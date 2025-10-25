<script lang="ts">
  export let title: string;
  export let description: string;
  export let bullets: string[] = [];
  export let imageLabel: string;
  export let reverse = false;
</script>

<section class="section">
  <div class="container feature {reverse ? 'reverse' : ''}">
    <div class="feature-visual" aria-hidden="true">
      <div class="feature-card">
        <div class="feature-label">{imageLabel}</div>
        <div class="feature-bars">
          <div class="feature-line"></div>
          <div class="feature-line short"></div>
          <div class="feature-line medium"></div>
          <div class="feature-line"></div>
          <div class="feature-line short"></div>
        </div>
      </div>
    </div>
    <div class="feature-copy">
      <h2>{title}</h2>
      <p>{description}</p>
      <ul>
        {#each bullets as bullet}
          <li>{bullet}</li>
        {/each}
      </ul>
    </div>
  </div>
</section>

<style>
  .feature {
    display: grid;
    gap: clamp(2rem, 4vw, 3rem);
    align-items: center;
  }

  @media (min-width: 900px) {
    .feature {
      grid-template-columns: repeat(2, minmax(0, 1fr));
    }

    .feature.reverse {
      direction: rtl;
    }

    .feature.reverse > * {
      direction: ltr;
    }
  }

  .feature-copy p {
    color: #4b5563;
    font-size: 1rem;
  }

  .feature-visual {
    position: relative;
    padding: clamp(1.5rem, 3vw, 2.5rem);
  }

  .feature-visual::before {
    content: '';
    position: absolute;
    inset: 1.5rem -8% -8% 8%;
    background: radial-gradient(circle at top left, rgba(0, 92, 230, 0.15), transparent 60%),
      radial-gradient(circle at bottom right, rgba(0, 196, 140, 0.18), transparent 55%);
    z-index: -2;
  }

  .feature-card {
    border-radius: 1.5rem;
    padding: 2rem;
    background: #ffffff;
    box-shadow: 0 24px 60px rgba(0, 92, 230, 0.15);
    display: flex;
    flex-direction: column;
    gap: 1.35rem;
  }

  .feature-label {
    display: inline-flex;
    align-items: center;
    justify-content: flex-start;
    align-self: flex-start;
    padding: 0.5rem 0.9rem;
    border-radius: 0.75rem;
    background: rgba(0, 92, 230, 0.08);
    color: var(--color-primary);
    font-weight: 600;
    font-size: 0.9rem;
  }

  .feature-bars {
    display: grid;
    gap: 0.65rem;
  }

  .feature-line {
    height: 14px;
    border-radius: 8px;
    background: linear-gradient(90deg, rgba(0, 92, 230, 0.85), rgba(0, 196, 140, 0.8));
  }

  .feature-line.short {
    width: 50%;
    background: rgba(0, 92, 230, 0.25);
  }

  .feature-line.medium {
    width: 70%;
    background: rgba(0, 196, 140, 0.3);
  }
</style>
