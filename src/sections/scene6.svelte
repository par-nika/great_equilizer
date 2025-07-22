<script>
  const title = "The Invisible Safety Net";
  const embedCode = `
    <iframe src='https://flo.uri.sh/visualisation/24339211/embed' title='Interactive or visual content' class='flourish-embed-iframe' frameborder='0' scrolling='no' style='width:100%;height:600px;' sandbox='allow-same-origin allow-forms allow-scripts allow-downloads allow-popups allow-popups-to-escape-sandbox allow-top-navigation-by-user-activation'></iframe>
    <div style='width:100%!;margin-top:4px!important;text-align:right!important;'>
      <a class='flourish-credit' href='https://public.flourish.studio/visualisation/24339211/?utm_source=embed&utm_campaign=visualisation/24339211' target='_top' style='text-decoration:none!important'>
        <img alt='Made with Flourish' src='https://public.flourish.studio/resources/made_with_flourish.svg' style='width:105px!important;height:16px!important;border:none!important;margin:0!important;'>
      </a>
    </div>
  `;
</script>

<section class="scene6">
  <h2>{title}</h2>

  <div class="scene-narrative">
    <p>
      Behind every successful college student, there's often a hidden web of support —
      family who can help pay for tuition, cover rent during internships, or offer a loan when jobs fall through.
    </p>

    <p>
      But for many Black families, that safety net simply doesn’t exist.
    </p>

    <div class="support-compare">
      <div class="group">
        <h3>White students are more likely to:</h3>
        <ul>
          <li>Receive financial help from parents</li>
          <li>Graduate without debt</li>
          <li>Inherit property or wealth</li>
          <li>Rely on family during emergencies</li>
        </ul>
      </div>

      <div class="group">
        <h3>Black students are more likely to:</h3>
        <ul>
          <li>Support family members financially — even while in school</li>
          <li>Graduate with higher debt and fewer job leads</li>
          <li>Be the first in their family to build wealth</li>
        </ul>
      </div>
    </div>

    <p>
      This isn't about individual resilience. It's about the structural absence of intergenerational wealth.
      When one group starts with a ladder and the other starts in a hole, the outcome isn't just unfair — it's inevitable.
    </p>
  </div>

  <div class="chart-container">
    {@html embedCode}
    <div class="source"><a href="https://public.tableau.com/views/BWDC-AssetsDebt-ADT13_17387909018670/ADT13?:language=en-US&padding=0&:embed=y&:sid=&:redirect=auth&:origin=viz_share_link&publish=yes&:display_count=n&position=relative"><i><u>Source: Black Wealth Data Center: Percent of 18-28 Year Olds who have Recieved Gift or Inheritance by Race/Ethnicity</u></i></a></div>
  </div>

  <p class="closing-note">
    These differences aren't just symbolic. They're cumulative — growing with every unpaid internship,
    every unexpected emergency, and every lost opportunity to invest.
  </p>
</section>

<style>
  .scene6 {
    background: #3D0814;
    color: #D8DCFF;
    font-family: 'Epilogue', sans-serif;
    padding: 2rem 8vw;
    text-align: center;
    margin-bottom: 10rem;
  }

  .scene6 h2 {
    font-size: 2.5rem;
    font-weight: 800;
    font-family: 'Bricolage Grotesque', sans-serif;
    color: #F8B31F;
    margin-bottom: 3rem;
  }

  .scene-narrative p {
    font-size: 1.2rem;
    line-height: 1.8;
    margin: 2rem auto;
    max-width: 1000px;
    text-align: left;
  }

  .support-compare {
    display: flex;
    justify-content: space-between;
    gap: 3rem;
    margin: 3rem 0;
    text-align: left;
    flex-wrap: wrap;
  }

  .support-compare .group {
    background: #442F38;
    border-radius: 12px;
    padding: 2rem;
    flex: 1;
    min-width: 280px;
    box-shadow: 0 0 12px rgba(0,0,0,0.1);
  }

  .support-compare h3 {
    font-size: 1.3rem;
    margin-bottom: 1rem;
    color: #F8B31F;
  }

  .support-compare ul {
    list-style-type: "🔸";
    padding-left: 1.2rem;
  }

  .support-compare li {
    font-size: 1.1rem;
    margin-bottom: 0.8rem;
    line-height: 1.6;
  }

  .chart-container {
    margin-top: 4rem;
    border-radius: 12px;
    overflow: hidden;
  }

  .closing-note {
    font-size: 1.1rem;
    color: #D8DCFF;
    max-width: 1000px;
    margin: 3rem auto 0;
    line-height: 1.6;
    text-align: center;
    opacity: 0.95;
  }

  @media (max-width: 768px) {
    .support-compare {
      flex-direction: column;
    }

    .scene6 h2 {
      font-size: 2rem;
    }

    .scene-narrative p {
      font-size: 1.05rem;
    }

    .support-compare h3 {
      font-size: 1.15rem;
    }

    .support-compare li {
      font-size: 1rem;
    }

    .closing-note {
      font-size: 1rem;
    }
  }
</style>
