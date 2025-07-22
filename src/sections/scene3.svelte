<script>
  import { onMount, afterUpdate } from 'svelte';
  import scrollama from 'scrollama';

  let currentChartIndex = 0;

  const charts = [
    {
      title: "Median Annual Earnings: Less than High School",
      embedCode: `<iframe src='https://flo.uri.sh/visualisation/24320651/embed' title='Interactive or visual content' class='flourish-embed-iframe' frameborder='0' scrolling='no' style='width:100%;height:600px;' sandbox='allow-same-origin allow-forms allow-scripts allow-downloads allow-popups allow-popups-to-escape-sandbox allow-top-navigation-by-user-activation'></iframe>`
  },
    {
      title: "Median Annual Earnings: Bachelor's Degree",
      embedCode: `<iframe src='https://flo.uri.sh/visualisation/24314503/embed' title='Interactive or visual content' class='flourish-embed-iframe' frameborder='0' scrolling='no' style='width:100%;height:600px;' sandbox='allow-same-origin allow-forms allow-scripts allow-downloads allow-popups allow-popups-to-escape-sandbox allow-top-navigation-by-user-activation'></iframe>`
      },
    {
      title: "Median Annual Earnings: Master's Degree or Higher",
      embedCode: `<iframe src='https://flo.uri.sh/visualisation/24320554/embed' title='Interactive or visual content' class='flourish-embed-iframe' frameborder='0' scrolling='no' style='width:100%;height:600px;' sandbox='allow-same-origin allow-forms allow-scripts allow-downloads allow-popups allow-popups-to-escape-sandbox allow-top-navigation-by-user-activation'></iframe>`
    }
  ];

  onMount(() => {
    const scroller = scrollama();

    const handleResize = () => {
      const steps = document.querySelectorAll(".step");
      steps.forEach(step => {
        if (step instanceof HTMLElement) {
          step.style.height = `${Math.floor(window.innerHeight * 0.75)}px`;
        }
      });
      scroller.resize();
    };

    const handleStepEnter = (response) => {
      currentChartIndex = response.index;
      const allSteps = document.querySelectorAll(".step");
      allSteps.forEach((el, i) => {
        el.classList.toggle("is-active", i === response.index);
      });
    };

    handleResize();

    scroller
      .setup({
        step: ".step",
        offset: 0.4,
        debug: false
      })
      .onStepEnter(handleStepEnter);
  });

  afterUpdate(() => {
    // Call Flourish renderer whenever DOM updates with new chart
    // @ts-ignore
    if (typeof window !== 'undefined' && window.Flourish?.createAll) {
      // @ts-ignore
      window.Flourish.createAll();
    }
  });
</script>
<section id="info">
<h2>So, what's the real story?</h2>
  <p>
    We're taught that more education leads to more income.
    But what happens when that rule doesn't hold equally for everyone?
  </p>
  <p>
    In this section, we'll explore how income gaps between Black and White Americans persist across all education levels — from those without a high school diploma to those with advanced degrees.
    As the charts scroll by, take a moment to notice not just the earnings — but the <i>distance</i> between the lines.
  </p>
</section>
<section id="scrolly">
<article>
  <div class="step">
    <p>Even without a high school diploma, income gaps persist between racial groups.</p>
    <!-- svelte-ignore element_implicitly_closed -->
    <p>Between 2010 and 2022, Black Americans without a high school diploma consistently earned less than their White counterparts — often by $5,000 to $12,000 per year.
       While both groups saw modest income increases over time, the gap didn't close — it hovered or even widened. For example:
       <ul>
          <li>In 2010, the gap was ~$5,800.</li>
          <li>By 2022, it had grown to over $11,000.</li>
        </ul>
  </div>
  <div class="step">
    <p>With a bachelor's degree, the gap grows — white graduates earn far more on average.</p>
    <!-- svelte-ignore element_implicitly_closed -->
    <p>Even with a college degree, Black graduates earn significantly less than White graduates with the same credentials.
      <ul>
        <li>In 2010, a Black graduate earned $5,300 less than a White graduate.</li>
        <li>By 2022, that gap had grown to over $14,000 — nearly three months of lost income every year.</li>
      </ul>

      </div>
  <div class="step">
    <p>Advanced degrees don't close the gap either — in fact, the disparity often widens.</p>
    <!-- svelte-ignore element_implicitly_closed -->
    <p>
      You'd think a master's or PhD would finally be the great equalizer.
      But the data tells a different story. Black Americans with advanced degrees still earn less than White Americans with the same education level — by $8,000 to $12,000 annually in most years.
      <ul>
        <li>In 2016, Black advanced-degree holders earned ~$7,800 less.</li>
        <li>By 2022, the gap was still nearly $10,000.</li>
      </ul>

  </div>
</article>

<figure>
  <h3>{charts[currentChartIndex].title}</h3>
  <div class="chart-container">
    {@html charts[currentChartIndex].embedCode}
  </div>
  <div style='width:100%!;margin-top:4px!important;text-align:right!important;'><a class='flourish-credit' href='https://public.flourish.studio/visualisation/24320651/?utm_source=embed&utm_campaign=visualisation/24320651' target='_top' style='text-decoration:none!important'><img alt='Made with Flourish' src='https://public.flourish.studio/resources/made_with_flourish.svg' style='width:105px!important;height:16px!important;border:none!important;margin:0!important;'> </a></div>
  <div class="source"><a href="https://public.tableau.com/views/BWDC-EducationEmployment-MedianAnnualEarnings/2MedianAnnualEarnings?:language=en-US&padding=0&:embed=y&:sid=&:redirect=auth&:origin=viz_share_link&:display_count=n&position=relative"><i><u>Source: Black Wealth Data Center: Median Annual Earnings For Full-Time Workers by Race/Ethnicity</u></i></a></div>
</figure>
</section>
<section id="info">
    <p> This isn't a merit gap — this is a system gap. </p>
    <p>
      The data shows that even with the same education, Black Americans consistently earn less than White Americans.
      This isn't about effort or ability — it's about the systems that keep Black Americans locked out of wealth-building opportunities.
    </p>
    <p>
      In the next section, we'll explore how these income gaps translate into wealth gaps — and why education alone isn't enough to close the racial wealth divide.
    </p>
</section>

<style>
#scrolly {
display: flex;
flex-direction: row;
gap: 2rem;
padding: 4rem 8vw;
background: #3D0814;
color: #D8DCFF;
font-family: 'Epilogue', sans-serif;
}
#info {
  background-color: #3D0814; /* Chocolate Cosmos */
  color: #D8DCFF; /* Periwinkle */
  padding: 10vh 10vw;
  font-family: 'Epilogue', sans-serif;
  transition: all 2s ease-in-out;
}

article {
flex: 1;
max-width: 26rem;
}

.step {
padding: 1.5rem;
background: #442F38;
border-left: 6px solid #F33D00;
border-radius: 8px;
margin-bottom: 2rem;
}



.step p {
font-size: 1.1rem;
line-height: 1.7;
}

figure {
flex: 2;
position: sticky;
top: 10%;
height: 75vh;
display: flex;
flex-direction: column;
justify-content: flex-start;
align-items: center;
background: #442F38;
border-radius: 12px;
padding: 2rem;
box-shadow: 0 0 20px rgba(0, 0, 0, 0.2);
}


.chart-container {
width: 100%;
height: 100%;
max-width: 100%;
overflow: hidden;
display: flex;
justify-content: bottom;
align-items: bottom;
border-radius: 12px;
box-sizing: border-box;
}

.chart-container :global(.flourish-embed-iframe) {
border: none;
border-radius: 12px;
box-sizing: border-box;
display: bottom;
max-width: 100%;
max-height: 100%;
position: bottom;
}

.source {
  font-size: 0.95rem;
  color: #a7a2b2;
  text-align: left;
  margin-bottom: 2rem;
  padding-left: 0.5rem;
}



@media (max-width: 768px) {
#scrolly {
  flex-direction: column;
  padding: 2rem;
}

figure {
  position: relative;
  top: unset;
  height: auto;
  margin-top: 2rem;
}

}

</style>
