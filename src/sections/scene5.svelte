<script>
  import Scroller from "../lib/Scroller.svelte";
  import ObservedArticleText from "../lib/ObservedArticleText.svelte";

  const options = {
    threshold: [0.85, 0.95],
  };

  const callback = (entries) => {
    entries.forEach((entry) => {
      const elem = entry.target;
      if (entry.intersectionRatio >= 0.9) {
        elem.style.backgroundColor = "#442F38";
      } else {
        elem.style.backgroundColor = "#3D0814";
      }
    });
  };
</script>

<section class="scene5">
<Scroller layout="left">
  {#snippet sticky()}
    <div>
      <h2>Education is a Burden, Not a Boost</h2>
      <p>
        Education is supposed to be the ladder to climb out of poverty.
        But for many Black families, it adds weight, not wings.
        It adds debt, delays, and disproportionate hardship.
      </p>
    </div>
  {/snippet}

  {#snippet scrolly()}
    <ObservedArticleText {callback} {options}>
      <strong>90% of Black students take out loans</strong> to pay for college — compared to 66% of white students.
      <br/><br/>
      It's not a financial head start—it's a burden Black students carry before their careers even begin.
      <br/><br/>
      <div class="source"><a href="https://dfpi.ca.gov/news/insights/student-loan-debt-a-disproportionate-burden-on-black-and-latino-borrowers/#:~:text=Subsequently%2C%2090%20percent%20of%20Black%20and%2072%20percent%20of%20Latino%20students%20take%20out%20student%20loans%2C%20compared%20to%2066%20percent%20of%20white%20borrowers."><i><u>Source: DFPI: Student Loan Debt: A Disproportionate Burden on Black and Latino Borrowers</u></i></a></div>
    </ObservedArticleText>

    <ObservedArticleText {callback} {options}>
      <strong>Average debt for Black bachelor's grads:</strong> $52,700+. The highest of any racial group.
      <br/><br/>
      And with lower starting incomes, that mountain of debt takes longer to climb—and hits harder every year.
      <br/><br/>
      <div class="source"><a href="https://educationdata.org/student-loan-debt-by-race#:~:text=Black%20and%20African%20American%20bachelor%E2%80%99s%20degree%20holders%20have%20an%20average%20of%20%2452%2C726%20in%20student%20loan%20debt."><i><u>Source: Education Data Initiative: Student Loan Debt by Race</u></i></a></div>
    </ObservedArticleText>

    <ObservedArticleText {callback} {options}>
      <strong>17% of Black grads are behind on student loans</strong> compared to 9% of white grads.
      <br/><br/>
      Missed payments, rising interest, lower credit scores—debt becomes a trap, not a tool.
      <br/><br/>
      <div class="source"><a href="https://www.consumerfinance.gov/consumer-tools/student-loans/data-and-research/"><i><u>Source: Consumer Financial Protection Bureau: Student Loan Data</u></i></a></div>
    </ObservedArticleText>

    <ObservedArticleText {callback} {options}>
      <strong>7% of Black young adults (18-28) received an inheritance</strong>. That's less than half the rate of white peers (16%).
      <br/><br/>
      Even when wealth is passed down, Black families often need to share it across generations—supporting parents and siblings left behind by Jim Crow and systemic exclusion.
      <br/><br/>
      <div class="source"><a href="https://www.census.gov/data/tables/time-series/demo/income-poverty/historical-income-inequality.html"><i><u>Source: Census Bureau: Historical Income Inequality</u></i></a></div>
      </ObservedArticleText>

    <ObservedArticleText {callback} {options}>
      <strong>FAFSA doesn't count home equity or retirement savings</strong>—assets white families are more likely to have.
      <br/><br/>
      That means <em>more grant aid</em> and <em>less debt</em> for white students—even when household incomes appear similar on paper.
      <br/><br/>
      <div class="source"><a href="https://www.consumerfinance.gov/consumer-tools/student-loans/data-and-research/"><i><u>Source: Consumer Financial Protection Bureau: Student Loan Data</u></i></a></div>
    </ObservedArticleText>

    <ObservedArticleText {callback} {options}>
      <strong>White families use 91% of inheritance to grow wealth.</strong> Black families? Just 20%.
      <br/><br/>
      Why? Because they're paying it forward—covering basic needs for loved ones locked out of opportunity.
      <br/><br/>
      <div class="source"><a href="https://www.census.gov/data/tables/time-series/demo/income-poverty/historical-income-inequality.html"><i><u>Source: Census Bureau: Historical Income Inequality</u></i></a></div>
    </ObservedArticleText>
  {/snippet}
</Scroller>
</section>

<style>
.scene5 {
background: #3D0814;
color: #D8DCFF;
font-family: 'Epilogue', sans-serif;
min-height: 100vh;
padding: 4rem 8vw;
margin-top: 20rem;
margin-bottom: 10rem;
transition: all 0.5s ease-in-out;
}
.scene5 h2 {
font-size: 2.8rem;
font-weight: 900;
font-family: 'Bricolage Grotesque', sans-serif;
color: #F8B31F;
margin-bottom: 2rem;
text-align: center;
padding-left: 3rem;
}
.scene5 p {
font-size: 1.25rem;
line-height: 1.8;
margin: 2rem 0;
padding-left: 3rem;
}
.source {
  font-size: 0.95rem;
  color: #a7a2b2;
  text-align: left;
  margin-bottom: 2rem;
  padding-left: 0.5rem;
}

@media (max-width: 768px) {
.scene5 {
  padding: 2rem 1.5rem;
}
.scene5 h2 {
  font-size: 2.1rem;
}
.scene5 p {
  font-size: 1.05rem;
}
}
</style>
