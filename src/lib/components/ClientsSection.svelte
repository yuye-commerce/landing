<script lang="ts">
  export let clientData: {
    title: string;
    clients: Array<{ src: string; name: string; desc: string }>;
  };
</script>

<section class="my-16 flex flex-col items-center">
  <div class="max-w-[900px]">
    <h2 class="font-bold text-2xl text-center mb-8">
      {clientData.title}
    </h2>
    <div
      class="grid grid-cols-1 sm:grid-cols-2 gap-6 transition-all duration-300"
    >
      {#each clientData.clients as client}
        <div class="p-4 flex space-x-4 rounded-2xl hover:shadow-md transition">
          <div class="text-primary w-28 h-28 shrink-0">
            <img src={client.src} alt="ảnh khách" class="rounded-xl" />
          </div>
          <div>
            <h3 class="font-semibold text-lg">{client.name}</h3>
            <p class="text-gray-600 leading-relaxed">{client.desc}</p>
          </div>
        </div>
      {/each}
    </div>
  </div>
</section>

<style>
</style>
