<script>
  import { fade } from 'svelte/transition';

  let quote = `\"According to the most recent data from the Federal Reserve in 2019,
  a median White family had a wealth of 8 times the wealth of the median Black family.
  The absolute differences are far greater if you look at the average, or the mean.\""`;

  let source = `Source: Virtual Hearing before the Joint Economic Committee of the U.S. Congress, May 12, 2021`;

</script>

<section class="scene2" in:fade={{ duration: 800 }}>
  <h2>So… is education really the great equalizer?</h2>

  <p>
    We're told that college is the golden ticket.
    That higher education can pull families out of poverty, erase centuries of disadvantage, and give everyone — regardless of race — a fair shot at success.
    But that's the <strong>myth</strong>. The reality is more complicated.
    Education <i>should</i> be the great equalizer.
    But it can't be — not when the starting lines are generations apart.
  </p>


  <blockquote>{quote}</blockquote>
  <div class="source"><i><u><a href="https://www.congress.gov/117/chrg/CHRG-117shrg45210/CHRG-117shrg45210.pdf?utm_source=chatgpt.com">{source}</a></u></i></div>

  <p>
    This isn't about effort. It's about systems. And the deeper we dig, the clearer the cracks become.
  </p>
  <p>
    And when you begin to examine how Black Americans have been systematically shut out of wealth-building opportunities, the cracks in that education-equals-equality narrative start to show.
  </p>
  <p>
    In this story, I'm digging into the data behind the racial wealth gap.
    Specifically: Why Black families, even with college degrees, often struggle to build wealth at the same pace as White families — and why education alone isn't enough to bridge that divide.
  </p>
</section>

<style>
  .scene2 {
    margin-top: 20rem;
    background-color: #3D0814; /* Chocolate Cosmos */
    color: #D8DCFF; /* Periwinkle */
    padding: 10vh 10vw;
    font-family: 'Epilogue', sans-serif;
    transition: all 2s ease-in-out;
    margin-bottom: 20rem;
  }

  .scene2 h2 {
    font-size: 2.8rem;
    font-weight: 900;
    color: #F8B31F; /* Xanthous */
    font-family: 'Bricolage Grotesque', sans-serif;
    margin-bottom: 2rem;
    text-align: center;
  }

  .scene2 p {
    font-size: 1.25rem;
    line-height: 1.8;
    margin: 2rem 0;
  }

  .scene2 blockquote {
    font-style: italic;
    background-color: #442F38; /* Eggplant */
    padding: 1.2rem 1.5rem;
    border-left: 6px solid #F33D00; /* Coquelicot */
    border-radius: 8px;
    color: #F8B31F;
    margin: 3rem 0 1rem;
    font-size: 1.1rem;
    max-width: 900px;
  }

  .scene2 .source {
    font-size: 0.95rem;
    color: #a7a2b2;
    text-align: left;
    margin-bottom: 2rem;
    padding-left: 0.5rem;
  }

  @media (max-width: 768px) {
    .scene2 {
      padding: 5vh 1.5rem;
    }

    .scene2 h2 {
      font-size: 2.1rem;
    }

    .scene2 p,
    .scene2 blockquote {
      font-size: 1.05rem;
    }
  }
</style>