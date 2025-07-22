<script>
  import { onMount } from "svelte";

  let { children, callback, options } = $props();

  // this uniqueId just lets us target the element
  // with `document.getElementById(uniqueId)` later on.
  // it's a little hacky, but it works.
  let uniqueId = Math.random().toString();

  // here we define the onMount() function for this component.
  // svelte handles calling the onMount() function *after* all of the HTML in this
  // component has been mounted to the DOM. we have to put the intersection observer
  // stuff in onMount() because we need to target the <div> we create below,
  // but it won't actually exist in the DOM until it's been mounted.
  onMount(() => {
      let intersectionObserver = new IntersectionObserver(callback, options);

      const observedElement = document.getElementById(uniqueId);
      intersectionObserver.observe(observedElement);
  });
</script>

<!-- assign the containing div the id `uniqueId` so we can target it -->
<div id={uniqueId} class="article-text">
  <p>
      {@render children()}
  </p>
</div>

<style>
  .article-text {
    max-width: 720px;
    margin: 2rem auto;
    padding: 2rem;
    background: #442F38;
    color: #F8F8FF;
    border-radius: 12px;
    font-family: 'Epilogue', sans-serif;
    font-size: 1.125rem;
    line-height: 1.7;
    transition: background 0.4s ease, color 0.4s ease;
  }

  @media (max-width: 768px) {
    .article-text {
      padding: 1.25rem;
      font-size: 1rem;
      width: 90%;
    }
  }
</style>
