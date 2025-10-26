<script lang="ts">
  export let benefitData: {
    header: string;
    benefits: Array<{ icon: any; title: string; description: string }>;
  };
</script>

<section class="my-16 flex flex-col items-center">
  <div class="max-w-[900px] mx-12">
    <h2 class="font-bold text-2xl text-center my-14">
      {benefitData.header}
    </h2>

    <div class="sector-grid">
      {#each benefitData.benefits as benefit}
        <article class="sector-card">
          <div class="flex items-center justify-center mb-4">
            <svelte:component
              this={benefit.icon}
              size={48}
              color="var(--primary)"
            />
          </div>

          <h3 class="font-bold text-center">
            {benefit.title}
          </h3>
          <p class="mt-4 text-center">
            {benefit.description}
          </p>
        </article>
      {/each}
    </div>
  </div>
</section>

<style>
  .sector-grid {
    display: grid;
    gap: 1.5rem;
  }

  @media (min-width: 720px) {
    .sector-grid {
      grid-template-columns: repeat(3, minmax(0, 1fr));
    }
  }

  .sector-card {
    background: #ffffff;
    border-radius: 1rem;
    padding: 1.75rem;
    box-shadow: 0 20px 45px rgba(15, 68, 142, 0.08);
    border: 1px solid rgba(226, 232, 240, 0.8);
    transition:
      transform 0.2s ease,
      box-shadow 0.2s ease;
  }

  .sector-card:hover {
    transform: translateY(-6px);
    box-shadow: 0 30px 60px rgba(15, 68, 142, 0.12);
  }

  .sector-card h3 {
    font-size: 1.15rem;
  }

  .sector-card p {
    font-size: 0.98rem;
  }
</style>
