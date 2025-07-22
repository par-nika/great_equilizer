<script>
  let titleVisible = false;
  let textVisible = false;

  // Use intersection observer to trigger fade-ins
  import { onMount } from 'svelte';

  onMount(() => {
    const titleObserver = new IntersectionObserver(
      ([entry]) => {
        if (entry.isIntersecting) titleVisible = true;
      },
      { threshold: 0.5 }
    );

    const textObserver = new IntersectionObserver(
      ([entry]) => {
        if (entry.isIntersecting) textVisible = true;
      },
      { threshold: 0.4 }
    );

    const titleEl = document.querySelector('.scene-title');
    const textEl = document.querySelector('.scene-narrative');

    if (titleEl) titleObserver.observe(titleEl);
    if (textEl) textObserver.observe(textEl);
  });
</script>

<section class="scene4">
  <h2 class="scene-title {titleVisible ? 'visible' : ''}">
    It's Not Just What You Earn — It's What You Keep
  </h2>

  <div class="scene-narrative {textVisible ? 'visible' : ''}">
    Income tells you how much you make in a year.
    <br>
    But <strong>wealth</strong> — that tells the <i>real</i> story.
    <br>
    It's what lets you buy a home. Pay for college. Ride out emergencies. Pass something on.
    <br>
    We like to believe that higher education builds that kind of financial security.
    <br>
    But for Black families, the data tells a harder truth.
    <br>
  </div>
  <div class="flourish-embed">
    {@html `<iframe src='https://flo.uri.sh/visualisation/24339001/embed' title='Interactive or visual content' class='flourish-embed-iframe' frameborder='0' scrolling='no' style='width:100%;height:600px;' sandbox='allow-same-origin allow-forms allow-scripts allow-downloads allow-popups allow-popups-to-escape-sandbox allow-top-navigation-by-user-activation'></iframe><div style='width:100%!;margin-top:4px!important;text-align:right!important;'><a class='flourish-credit' href='https://public.flourish.studio/visualisation/24339001/?utm_source=embed&utm_campaign=visualisation/24339001' target='_top' style='text-decoration:none!important'><img alt='Made with Flourish' src='https://public.flourish.studio/resources/made_with_flourish.svg' style='width:105px!important;height:16px!important;border:none!important;margin:0!important;'> </a></div>`}
    <div class="source"><a href="https://public.tableau.com/views/BWDC-AssetsDebt-SCFTimeSeries/SCFTimeSeries?:language=en-US&padding=0&:embed=y&:sid=&:redirect=auth&:origin=viz_share_link&:display_count=n&position=relative"><i><u>Source: Black Wealth Data Center: Median Total Net Worth of Households by Race/Ethnicity</u></i></a></div>
  </div>

  <div class="scene-narrative {textVisible ? 'visible' : ''}">
    <ul style="text-align: left;">
      <li>While the wealth of White families climbs decade by decade, Black wealth stays almost flat.</li>
      <li>White families don't just have more — their wealth <i>grows faster</i> over time.</li>
      <li>Black net worth is stagnant — barely moving, and always trailing far behind.</li>
    </ul>
    <br>
    This isn't about hard work or higher degrees.
    This is about a system where what you <i>earn</i> doesn't translate into what you <i>keep</i>.
    <br>
  </div>
</section>

<!-- svelte-ignore css_unused_selector -->
<style>
.scene4 {
  padding: 4rem 8vw;
  background-color: #3D0814; /* Chocolate Cosmos */
  color: #D8DCFF; /* Periwinkle */
  font-family: 'Epilogue', sans-serif;
  min-height: 100vh;
  margin-top: 10rem;
  margin-bottom: 20rem;
  transition: all 0.5s ease-in-out;
}

.scene-title {
  font-size: 2.8rem;
  font-weight: 900;
  font-family: 'Bricolage Grotesque', sans-serif;
  color: #F8B31F; /* Xanthous */
  margin-bottom: 2rem;
  text-align: center;
  opacity: 0;
  transition: opacity 1s ease-in-out;
}

.scene-title.visible {
  opacity: 1;
}

.scene-narrative {
  max-width: 900px;
  margin: 1.5rem auto;
  font-size: 1.25rem;
  line-height: 1.8;
  text-align: center;
  opacity: 0;
  transition: opacity 1.2s ease-in-out;
  color: #D8DCFF;
}

.scene-narrative.visible {
  opacity: 1;
}

.quote {
  font-style: italic;
  margin-top: 2rem;
  font-size: 1.1rem;
  text-align: center;
  color: #F8B31F;
}

.flourish-embed {
  margin: 3rem auto 1rem;
  max-width: 900px;
  background: #442F38;
  border-radius: 12px;
  padding: 2rem;
  box-shadow: 0 0 20px rgba(0, 0, 0, 0.2);
}
.source {
  font-size: 0.95rem;
  color: #a7a2b2;
  text-align: left;
  margin-bottom: 2rem;
  padding-left: 0.5rem;
}

iframe {
  width: 100%;
  height: 600px;
  border: none;
  border-radius: 12px;
  background: #442F38;
}

@media (max-width: 768px) {
  .scene4 {
    padding: 2rem 1.5rem;
  }
  .scene-title {
    font-size: 2.1rem;
  }
  .scene-narrative {
    font-size: 1.05rem;
  }
  .flourish-embed {
    padding: 1rem;
  }
  iframe {
    height: 350px;
  }
}
</style>