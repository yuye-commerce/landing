<script lang="ts">
  export let sectorTitle: string;
  export let sectorDescription: string;
  export let sectors: Array<{ title: string; description: string }> = [];
</script>

<section class="section section-alt">
  <div class="container">
    <div class="section-heading">
      <h2 class="font-bold text-2xl">
        {sectorTitle}
      </h2>
      <p>
        {@html sectorDescription}
      </p>
    </div>
    <div class="sector-grid">
      {#each sectors as sector}
        <article class="sector-card">
          <h3 class="font-bold">{sector.title}</h3>
          <p>{sector.description}</p>
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
    color: #4b5563;
    font-size: 0.98rem;
  }
</style>
