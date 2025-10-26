<script lang="ts">
  import { onMount } from "svelte";
  import * as Item from "$lib/components/ui/item";
  export let sectorData: {
    title: string;
    description: string;
    sectors: Array<{ title: string; icon: any }>;
  };

  let showAll = false;
  let isMobile = false;

  const visibleCount = 4; // number of items to show on mobile before "Show more"

  // Track screen size
  function checkIsMobile() {
    isMobile = window.innerWidth < 640; // Tailwind 'sm' breakpoint
  }

  onMount(() => {
    checkIsMobile();
    window.addEventListener("resize", checkIsMobile);
    return () => window.removeEventListener("resize", checkIsMobile);
  });
</script>

<section class="my-20 flex flex-col items-center">
  <div class="max-w-[900px] w-full px-6">
    <div class="section-heading text-center mb-12">
      <h2 class="font-bold text-2xl mb-4">
        {@html sectorData.title}
      </h2>
      <p class="text-gray-600 leading-relaxed">
        {@html sectorData.description}
      </p>
    </div>

    <!-- Grid of items -->
    <div
      class="grid grid-cols-1 sm:grid-cols-2 gap-6 transition-all duration-300"
    >
      {#each sectorData.sectors as sector, i (sector.title)}
        {#if !isMobile || showAll || i < visibleCount}
          <Item.Root
            variant="outline"
            class="p-4 flex items-center space-x-4 rounded-2xl hover:shadow-md transition"
          >
            <Item.Media variant="icon" class="text-primary w-10 h-10 shrink-0">
              <svelte:component this={sector.icon} />
            </Item.Media>
            <Item.Content>
              <Item.Title class="font-semibold text-lg">
                {sector.title}
              </Item.Title>
            </Item.Content>
          </Item.Root>
        {/if}
      {/each}
    </div>

    <!-- "Show more" button: only on mobile and if there are more items -->
    {#if isMobile && sectorData.sectors.length > visibleCount}
      <div class="mt-8 flex justify-center">
        <button
          class="text-primary font-medium border border-primary px-5 py-2 rounded-full hover:bg-primary hover:text-white transition"
          on:click={() => (showAll = !showAll)}
        >
          {showAll ? "Thu gọn" : "Xem thêm"}
        </button>
      </div>
    {/if}
  </div>
</section>

<style>
</style>
