<script lang="ts">
  export let headline: string;
  export let subheadline: string;
  export let highlight: string;
  export let ctaText: string;
  export let ctaHref: string;
  export let heroStats: Array<{ label: string; value: string }> = [];
  export let heroFunctions: Array<{
    icon: any;
    title: string;
  }> = [];

  import { Button } from "$lib/components/ui/button";
  import Download from "@lucide/svelte/icons/download";
  import * as Item from "$lib/components/ui/item/index.js";
</script>

<section class="hero section">
  <div class="container hero-inner">
    <div class="hero-copy">
      <span class="hero-kicker">{highlight}</span>
      <h1>{headline}</h1>
      <div class="hero-cta">
        <Button size="lg" class="p-6">
          <Download />
          {ctaText}
        </Button>
      </div>
      <p class="hero-sub">{subheadline}</p>
      <div class="hero-stats">
        {#each heroStats as stat}
          <div class="stat">
            <span class="stat-value">{stat.value}</span>
            <span class="stat-label">{stat.label}</span>
          </div>
        {/each}
      </div>
    </div>
    <div class="grid grid-cols-3 md:grid-cols-2 lg:grid-cols-1 gap-4">
      {#each heroFunctions as func}
        <Item.Root
          variant="outline"
          class="bg-[linear-gradient(109deg,rgba(0,92,230,0.1),rgba(0,196,140,0.15))]"
        >
          <Item.Media variant="icon">
            <svelte:component this={func.icon} />
          </Item.Media>
          <Item.Content>
            <Item.Title>{func.title}</Item.Title>
          </Item.Content>
        </Item.Root>
      {/each}
    </div>
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
    width: 100%;
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
</style>
