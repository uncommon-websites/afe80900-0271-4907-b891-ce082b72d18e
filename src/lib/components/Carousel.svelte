<script lang="ts">
  const images = [
    "https://images.unsplash.com/photo-1558002038-1055907df827?q=80&w=2070&auto=format&fit=crop",
    "https://images.unsplash.com/photo-1556909114-f6e7ad7d3136?q=80&w=2070&auto=format&fit=crop",
    "https://images.unsplash.com/photo-1585128792020-803d29415281?q=80&w=2070&auto=format&fit=crop"
  ];
</script>

<section class="bg-white pb-24 overflow-hidden">
  <div class="flex gap-4 overflow-x-auto px-6 pb-8 snap-x">
    {#each images as img}
      <div class="min-w-[80vw] md:min-w-[60vw] lg:min-w-[45vw] h-[400px] snap-center first:pl-0">
        <img src={img} alt="Smart home installation" class="w-full h-full object-cover rounded-lg" />
      </div>
    {/each}
  </div>
  
  <div class="text-center mt-4">
    <p class="text-gray-500 text-sm mb-4">Our work across services <span class="text-gray-400">Technology • Media • Real Estate</span></p>
    <div class="flex justify-center gap-2">
      <div class="w-1.5 h-1.5 rounded-full bg-gray-800"></div>
      <div class="w-1.5 h-1.5 rounded-full bg-gray-300"></div>
      <div class="w-1.5 h-1.5 rounded-full bg-gray-300"></div>
    </div>
  </div>
</section>
