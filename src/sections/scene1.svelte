<script>
  import { onMount } from 'svelte';


  const title = "The Great Equilizer Myth: Education";
  const subtitle = "How Education Fails to Close the Racial Wealth Gap";

  const scrollNarrative = [
  "It's often said: \"Just get a college degree — that'll solve everything.\"",
  "It's a promise woven into the American Dream: that education is the great equalizer, the ladder out of poverty — especially for Black Americans.",
  "But what if that promise is cracked?",
  "What if college doesn't actually level the playing field?",
  "because the field was never level to begin with.",
  "Let's see why."
  ];

  let scrollY = 0;
  let activeLine = 0;

  onMount(() => {
  const onScroll = () => {
    scrollY = window.scrollY;
    activeLine = Math.min(
      scrollNarrative.length,
      Math.floor(scrollY / 80)
    );
  };
  window.addEventListener('scroll', onScroll);
  return () => window.removeEventListener('scroll', onScroll);
});

</script>

<section>
  <h1>{title}</h1>
  <h2>{subtitle}</h2>

  {#each scrollNarrative as line, i}
    <div class="narrative-line {i < activeLine ? 'show' : ''}">
      {line}
    </div>
  {/each}
</section>

<style>

section {
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background: #3D0814; /* Chocolate cosmos */
  color: white;
  padding: 2rem;
  text-align: center;
  position: relative;
  overflow: hidden;
  padding-top: 20rem;
}

h1 {
  font-size: 4rem;
  font-weight: 900;
  font-family: "Bricolage Grotesque", sans-serif;
  color: #F8B31F; /* Xanthous */
  margin-bottom: 1rem;
}

h2 {
  font-size: 1.75rem;
  font-weight: 600;
  font-family: "Epilogue", sans-serif;
  color: #F8B31F; /* Also Xanthous, or switch to #D8DCFF for contrast */
  margin-bottom: 2rem;
}

.narrative-line {
  font-size: 1.5rem;
  font-family: "Epilogue", sans-serif;
  max-width: 50rem;
  margin: 1rem auto;
  opacity: 0;
  transition: opacity 0.8s ease-in-out;
}

.narrative-line.show {
  opacity: 1;
}
</style>