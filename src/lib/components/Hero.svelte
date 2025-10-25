<script lang="ts">
  export let headline: string;
  export let subheadline: string;
  export let highlight: string;
  export let ctaText: string;
  export let ctaHref: string;
  export let secondaryCta: { text: string; href: string } | undefined =
    undefined;
  export let heroStats: Array<{ label: string; value: string }> = [];

  import { Button } from "$lib/components/ui/button";
</script>

<section class="hero section">
  <div class="container hero-inner">
    <div class="hero-copy">
      <span class="hero-kicker">{highlight}</span>
      <h1>{headline}</h1>
      <p class="hero-sub">{subheadline}</p>
      <div class="hero-cta">
        <Button>
          {ctaText}
        </Button>
        <!-- <a class="btn" href={ctaHref}>{ctaText}</a> -->
        <!-- {#if secondaryCta} -->
        <!--   <a class="btn-secondary" href={secondaryCta.href} -->
        <!--     >{secondaryCta.text}</a -->
        <!--   > -->
        <!-- {/if} -->
      </div>
      {#if heroStats.length}
        <div class="hero-stats">
          {#each heroStats as stat}
            <div class="stat">
              <span class="stat-value">{stat.value}</span>
              <span class="stat-label">{stat.label}</span>
            </div>
          {/each}
        </div>
      {/if}
    </div>
    <div class="hero-visual" aria-hidden="true"></div>
  </div>
</section>

<style>
  .hero-inner {
    display: grid;
    gap: clamp(2rem, 4vw, 3rem);
    align-items: center;
  }

  @media (min-width: 900px) {
    .hero-inner {
      grid-template-columns: repeat(2, minmax(0, 1fr));
    }
  }

  .hero-copy {
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
  }

  .hero-kicker {
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    font-size: 0.85rem;
    color: var(--color-primary);
  }

  h1 {
    font-size: clamp(2.5rem, 6vw, 3.5rem);
    line-height: 1.1;
  }

  .hero-sub {
    font-size: clamp(1rem, 2.2vw, 1.2rem);
    color: #444c56;
  }

  .hero-cta {
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
    align-items: center;
  }

  .btn-secondary {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    padding: 0.85rem 1.75rem;
    border-radius: 0.5rem;
    font-weight: 600;
    background: transparent;
    color: var(--color-primary);
    border: 1.5px solid rgba(0, 92, 230, 0.4);
    transition:
      border-color 0.2s ease,
      color 0.2s ease,
      transform 0.2s ease;
  }

  .btn-secondary:hover {
    border-color: var(--color-primary);
    color: #0a4fc4;
    transform: translateY(-1px);
  }

  .hero-stats {
    display: grid;
    gap: 1rem;
    grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
    padding: 1.25rem;
    border-radius: 1rem;
    background: linear-gradient(
      109deg,
      rgba(0, 92, 230, 0.1),
      rgba(0, 196, 140, 0.15)
    );
  }

  .stat {
    display: flex;
    flex-direction: column;
    gap: 0.35rem;
  }

  .stat-value {
    font-size: 1.5rem;
    font-weight: 700;
    color: var(--color-primary);
  }

  .stat-label {
    font-size: 0.9rem;
    color: #4b5563;
  }

  .hero-visual {
    position: relative;
    isolation: isolate;
    padding: clamp(1.5rem, 3vw, 2.5rem);
  }

  .hero-visual::before {
    content: "";
    position: absolute;
    inset: 2rem -10% -10% 10%;
    background: radial-gradient(
        circle at top right,
        rgba(0, 92, 230, 0.2),
        transparent 60%
      ),
      radial-gradient(
        circle at bottom left,
        rgba(0, 196, 140, 0.2),
        transparent 55%
      );
    z-index: -2;
  }

  .hero-card {
    border-radius: 1.5rem;
    background: #ffffff;
    box-shadow: 0 30px 80px rgba(0, 92, 230, 0.18);
    overflow: hidden;
    display: flex;
    flex-direction: column;
    gap: 0;
  }

  .hero-card-header {
    display: flex;
    gap: 0.5rem;
    padding: 1.25rem;
    background: linear-gradient(
      120deg,
      rgba(0, 92, 230, 0.08),
      rgba(0, 196, 140, 0.08)
    );
  }

  .hero-pulse {
    width: 14px;
    height: 14px;
    border-radius: 50%;
    background: rgba(0, 92, 230, 0.35);
    animation: pulse 2.8s infinite ease-in-out;
  }

  .hero-pulse:nth-child(2) {
    animation-delay: 0.4s;
  }

  .hero-pulse:nth-child(3) {
    animation-delay: 0.8s;
  }

  @keyframes pulse {
    0%,
    100% {
      transform: scale(1);
      opacity: 0.7;
    }
    50% {
      transform: scale(1.25);
      opacity: 1;
    }
  }

  .hero-card-body {
    padding: 1.75rem;
    display: flex;
    flex-direction: column;
    gap: 1.75rem;
  }

  .hero-chart {
    display: grid;
    gap: 0.75rem;
    grid-template-columns: repeat(4, 1fr);
    align-items: end;
    height: 160px;
  }

  .bar {
    border-radius: 0.75rem 0.75rem 0.35rem 0.35rem;
    background: linear-gradient(
      180deg,
      rgba(0, 92, 230, 1),
      rgba(0, 92, 230, 0.65)
    );
  }

  .bar-two {
    height: 55%;
  }

  .bar-one {
    height: 35%;
    background: linear-gradient(
      180deg,
      rgba(0, 196, 140, 1),
      rgba(0, 196, 140, 0.6)
    );
  }

  .bar-three {
    height: 85%;
  }

  .bar-four {
    height: 70%;
  }

  .hero-summary {
    display: grid;
    gap: 1rem;
    background: rgba(0, 92, 230, 0.06);
    border-radius: 1rem;
    padding: 1.25rem;
  }

  .summary-label {
    display: block;
    font-size: 0.85rem;
    color: #4b5563;
  }

  .summary-value {
    display: block;
    font-weight: 600;
    color: var(--color-primary);
    font-size: 1.1rem;
  }
</style>
