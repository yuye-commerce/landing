<script lang="ts">
  export let quote: string;
  export let author: string;
  export let role: string;
  export let logos: string[] = [];
</script>

<section class="section">
  <div class="container clients">
    <div class="testimonial">
      <h2>Khách hàng tin dùng</h2>
      <blockquote>
        <p>{quote}</p>
        <cite>
          <span class="author">{author}</span>
          <span class="role">{role}</span>
        </cite>
      </blockquote>
    </div>
    <div class="logo-wall">
      {#each logos as logo}
        <span class="logo-pill">{logo}</span>
      {/each}
    </div>
  </div>
</section>

<style>
  .clients {
    display: grid;
    gap: clamp(2rem, 5vw, 3rem);
    align-items: center;
  }

  @media (min-width: 960px) {
    .clients {
      grid-template-columns: 1.1fr 1fr;
    }
  }

  blockquote {
    margin: 0;
    padding: 2rem;
    border-radius: 1.5rem;
    background: linear-gradient(135deg, rgba(0, 92, 230, 0.08), rgba(0, 196, 140, 0.12));
    box-shadow: inset 0 0 0 1px rgba(0, 92, 230, 0.15);
  }

  blockquote p {
    font-size: 1.1rem;
    color: #374151;
  }

  cite {
    display: flex;
    flex-direction: column;
    margin-top: 1.25rem;
    font-style: normal;
  }

  .author {
    font-weight: 600;
  }

  .role {
    color: #4b5563;
    font-size: 0.95rem;
  }

  .logo-wall {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(160px, 1fr));
    gap: 1rem;
    align-items: center;
  }

  .logo-pill {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    padding: 1rem 1.5rem;
    border-radius: 1rem;
    background: #ffffff;
    box-shadow: 0 12px 32px rgba(15, 68, 142, 0.12);
    color: #4b5563;
    font-weight: 600;
    font-size: 1rem;
  }
</style>
