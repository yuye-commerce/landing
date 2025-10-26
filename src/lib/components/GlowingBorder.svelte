<script>
  export let highlight = "";
  export let gradient = "#0000 0% 70%, var(--secondary)";
  export let filter = "glow-0";
  export let borderWidth = 6;
  export let margin = 2;
</script>

<div
  class="glow-container"
  style="--b: {borderWidth}px; --m: {margin}; --l: {gradient}; --f: url(#{filter})"
>
  <span
    class="px-4 py-2 font-semibold rounded-lg text-sm bg-white text-primary"
  >
    {highlight}
  </span>
</div>

<style>
  @property --a {
    syntax: "<angle>";
    initial-value: 0deg;
    inherits: false;
  }

  .glow-container {
    width: fit-content;
    border: solid var(--b) transparent;
    border-radius: calc(2 * var(--b));
    background: repeating-conic-gradient(from var(--a, 0deg), var(--l))
      border-box;
    filter: var(--f);
    animation: rotate 2s linear infinite;
  }

  @keyframes rotate {
    to {
      --a: 1turn;
    }
  }
</style>
