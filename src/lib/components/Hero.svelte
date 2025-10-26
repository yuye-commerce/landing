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
  import GlowingBorder from "$lib/components/GlowingBorder.svelte";
</script>

<section
  class="relative overflow-hidden bg-linear-to-bl from-primary via-white to-secondary py-16 md:py-24 rounded-b-4xl"
>
  <div class="container mx-auto px-4">
    <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 lg:gap-12 items-center">
      <!-- Left Content -->
      <div class="flex flex-col space-y-6">
        <GlowingBorder {highlight} />
        <h1
          class="text-4xl md:text-5xl lg:text-6xl font-bold text-gray-900 leading-tight"
        >
          {headline}
        </h1>

        <p class="text-lg md:text-xl text-gray-600 leading-relaxed">
          {subheadline}
        </p>

        <div class="pt-2">
          <Button size="lg" class="px-8 py-6 text-base">
            <Download class="mr-2 h-5 w-5" />
            {ctaText}
          </Button>
        </div>

        <!-- Stats Grid -->
        {#if heroStats.length > 0}
          <div class="grid grid-cols-2 md:grid-cols-3 gap-6 pt-6">
            {#each heroStats as stat}
              <div class="flex flex-col space-y-1">
                <span
                  class="text-2xl md:text-3xl font-bold bg-clip-text text-primary"
                >
                  {stat.value}
                </span>
                <span class="text-sm text-gray-600">
                  {stat.label}
                </span>
              </div>
            {/each}
          </div>
        {/if}
      </div>

      <!-- Right Image -->
      <div class="relative lg:order-last order-first lg:ml-8">
        <div class="relative rounded-2xl overflow-hidden shadow-2xl">
          <img
            src="https://placecats.com/800/600"
            alt="Hero illustration"
            class="w-full h-auto object-cover"
          />
          <!-- Gradient Overlay -->
          <div
            class="absolute inset-0 bg-linear-to-br from-blue-600/10 to-emerald-500/10 mix-blend-overlay"
          ></div>
        </div>

        <!-- Decorative Elements -->
        <div
          class="absolute -z-10 top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-[120%] h-[120%] bg-linear-to-br from-blue-200/30 to-emerald-200/30 rounded-full blur-3xl"
        ></div>
      </div>
    </div>
  </div>
</section>
