<script lang="ts">
  export let badges: Array<{ label: string; caption: string }> = [];
</script>

<div class="badge-row">
  {#each badges as badge}
    <div class="badge">
      <span class="badge-icon">↓</span>
      <div>
        <div class="badge-label">{badge.label}</div>
        <div class="badge-caption">{badge.caption}</div>
      </div>
    </div>
  {/each}
</div>

<style>
  .badge-label {
    font-weight: 600;
  }

  .badge-caption {
    font-size: 0.85rem;
    color: #4b5563;
  }
</style>
