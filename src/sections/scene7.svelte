<script>
  const title = "The Dream Needs Repair";
  const subtitle = "Why Closing the Racial Wealth Gap Takes More Than Degrees";

  const narrative = [
    "The racial wealth gap isn't a glitch — it's the result of generations of policy, practice, and prejudice.",
    "Hard work alone can't fix what policy broke.",
    "You can't earn your way out of a wealth gap built into housing markets, education systems, tax codes, and labor practices.",
    "This gap doesn't just hurt Black families. It holds back our whole economy — wasting talent, stalling growth, and limiting innovation.",
    "This isn't about charity. It's about justice. It's about rebuilding the ladder — not just telling people to climb harder.",
    "We need policy that sees the full picture:",
    ">> Count the assets FAFSA ignores — like home equity and retirement accounts.",
    ">> Fix how student loans are awarded, repaid, and forgiven — with racial equity in mind.",
    ">> Invest directly in Black communities — through housing, healthcare, education, and entrepreneurship.",
    ">> Tax wealth fairly. Make inheritance a tool for equity, not entrenchment.",
    ">> End the myth that education alone is the great equalizer — and build systems where it finally can be.",
    "The American Dream should not be gated by history. It should be rebuilt — accessible to all, grounded in truth, and powered by policy."
  ];
</script>

<section class="final-scroll-section">
  <h1>{title}</h1>
  <h2>{subtitle}</h2>

  {#each narrative as line}
    {#if line.startsWith(">>")}
      <div class="policy-box">
        {line.replace(">>", "").trim()}
      </div>
    {:else}
      <p class="narrative-text">{line}</p>
    {/if}
  {/each}
</section>

<style>
  .final-scroll-section {
    padding: 6rem 2rem;
    background: #3D0814;
    color: #D8DCFF;
    text-align: center;
    font-family: "Epilogue", sans-serif;
  }

  h1 {
    font-size: 3rem;
    font-weight: 900;
    font-family: "Bricolage Grotesque", sans-serif;
    color: #F8B31F;
    margin-bottom: 1rem;
  }

  h2 {
    font-size: 1.5rem;
    font-weight: 500;
    margin-bottom: 3rem;
    max-width: 70rem;
    margin-left: auto;
    margin-right: auto;
    color: #F8B31F;
  }

  .narrative-text {
    font-size: 1.25rem;
    max-width: 100rem;
    margin: 1.5rem auto;
    line-height: 1.8;
    transition: opacity 0.6s ease-in-out;
  }

  .policy-box {
    background-color: #442F38;
    border-left: 6px solid #F8B31F;
    padding: 1.2rem 1.5rem;
    margin: 1.5rem auto;
    font-size: 1.15rem;
    max-width: 70rem;
    border-radius: 8px;
    text-align: left;
    box-shadow: 0 2px 10px rgba(0,0,0,0.15);
    transition: background 0.3s, transform 0.3s;
  }

  .policy-box:hover {
    background-color: #5a3e47;
    transform: translateY(-2px);
  }

  @media (max-width: 768px) {
    h1 {
      font-size: 2.2rem;
    }

    h2 {
      font-size: 1.2rem;
    }

    .narrative-text {
      font-size: 1.05rem;
    }

    .policy-box {
      font-size: 1rem;
      padding: 1rem;
    }
  }
</style>
