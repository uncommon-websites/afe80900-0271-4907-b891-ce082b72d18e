<script lang="ts">
  let selectedService = $state(0);
  
  const services = [
    {
      title: 'Smart Home Automation',
      description: 'Complete integration for modern living.',
      image: 'https://images.unsplash.com/photo-1558002038-1055907df827?q=80&w=2070&auto=format&fit=crop',
      features: ['Lighting Control', 'Climate Management', 'Security Integration']
    },
    {
      title: 'Photography & Videography',
      description: 'Professional media for listings and businesses.',
      image: 'https://images.unsplash.com/photo-1542038784456-1ea8e935640e?q=80&w=2070&auto=format&fit=crop',
      features: ['Real Estate Listings', 'Commercial Projects', 'Event Coverage']
    },
    {
      title: 'Web Development',
      description: 'Modern websites that drive results.',
      image: 'https://images.unsplash.com/photo-1460925895917-afdab827c52f?q=80&w=2015&auto=format&fit=crop',
      features: ['Custom Design', 'E-commerce', 'SEO Optimization']
    },
    {
      title: 'Social Media Management',
      description: 'Build your brand and engage your audience.',
      image: 'https://images.unsplash.com/photo-1611162617474-5b21e879e113?q=80&w=2074&auto=format&fit=crop',
      features: ['Content Strategy', 'Community Management', 'Analytics & Growth']
    },
    {
      title: 'Real Estate Services',
      description: 'Expert guidance for buyers and sellers.',
      image: 'https://images.unsplash.com/photo-1560518883-ce09059eeffa?q=80&w=2073&auto=format&fit=crop',
      features: ['Property Sales', 'Market Analysis', 'Client Representation']
    },
    {
      title: 'Business Networking & Tech Support',
      description: 'Infrastructure and support for growing businesses.',
      image: 'https://images.unsplash.com/photo-1551434678-e076c223a692?q=80&w=2070&auto=format&fit=crop',
      features: ['Network Setup', 'IT Support', 'System Integration']
    }
  ];
  
  let currentService = $derived(services[selectedService]);
</script>

<section class="bg-[#f9f9f7] py-24 px-6" id="services">
  <div class="max-w-[1200px] mx-auto text-center">
    <h2 class="text-[40px] font-light text-gray-900 mb-16">
      Six core services. <span class="text-gray-400">Infinite possibilities.</span>
    </h2>

    <div class="mb-8">
      <h3 class="text-2xl font-normal mb-2">{currentService.title}</h3>
      <p class="text-gray-500 text-sm">{currentService.description}</p>
    </div>

    <!-- Service Showcase -->
    <div class="relative w-full h-[400px] bg-white rounded-xl mb-8 flex items-center justify-center overflow-hidden border border-gray-100">
      <div class="absolute inset-0 flex items-center justify-between px-4 z-10">
        <button 
          onclick={() => selectedService = (selectedService - 1 + services.length) % services.length}
          class="w-10 h-10 rounded-full bg-gray-100 flex items-center justify-center hover:bg-gray-200 transition-colors"
        >
          <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="m15 18-6-6 6-6"/></svg>
        </button>
        <button 
          onclick={() => selectedService = (selectedService + 1) % services.length}
          class="w-10 h-10 rounded-full bg-gray-100 flex items-center justify-center hover:bg-gray-200 transition-colors"
        >
          <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="m9 18 6-6-6-6"/></svg>
        </button>
      </div>
      <img src={currentService.image} class="h-[80%] object-contain" alt={currentService.title} />
    </div>

    <!-- Service Navigation Dots -->
    <div class="flex justify-center gap-2 mb-8">
      {#each services as service, index}
        <button 
          onclick={() => selectedService = index}
          class={[
            'w-2 h-2 rounded-full transition-all',
            selectedService === index ? 'bg-primary-600 w-8' : 'bg-gray-300 hover:bg-gray-400'
          ]}
          aria-label={`View ${service.title}`}
        ></button>
      {/each}
    </div>

    <div class="flex justify-center gap-8 text-sm text-gray-600 mb-4 border-b border-gray-200 pb-4 inline-flex mx-auto w-auto px-12">
      {#each currentService.features as feature}
        <span>{feature}</span>
      {/each}
    </div>

    <p class="text-xs text-gray-500 mb-8">
      Custom pricing based on your needs. <span class="font-bold text-gray-900">Transparent quotes.</span><br>
      Free consultation available for all services.
    </p>

    <div class="flex justify-center gap-4">
      <button class="px-6 py-3 bg-gray-100 hover:bg-gray-200 rounded-lg text-sm font-medium transition-colors text-left">
        <span class="block text-[10px] text-gray-500">Want to learn more?</span>
        <span class="text-primary-600">Explore all services</span>
      </button>
      <button class="px-6 py-3 bg-primary-600 hover:bg-primary-700 text-white rounded-lg text-sm font-medium transition-colors flex items-center gap-2">
        <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z"/></svg>
        Schedule consultation
      </button>
    </div>
  </div>
</section>
