<script lang="ts">
  import Header from "$lib/components/Header.svelte";
  import Section from "$lib/components/Section.svelte";
  
  const services = [
    "Psychiatric Evaluation & Medication Management",
    "Individual Psychotherapy",
    "Collaborative Care Coordination",
    "Treatment for Anxiety & Depression",
    "Support for High-Achievers & Perfectionism"
  ];

  const insights = [
    {
      date: "January 2025",
      title: "Understanding Perfectionism in High-Achieving Professionals",
      image: "/generated/image-diverse-group-of-nyc-professionals-in-a--1765660982952-6.webp"
    },
    {
      date: "December 2024",
      title: "The Benefits of Integrated Psychiatric and Psychotherapy Care",
      image: "/generated/image-professional-woman-smiling-genuinely-whi-1765660985137-7.webp"
    },
    {
      date: "November 2024",
      title: "Finding Mental Health Care That Feels Human in NYC",
      image: "/generated/image-peaceful-nyc-skyline-view-through-large--1765660987309-8.webp"
    }
  ];

  const values = [
    { name: "Human-Centered Care", desc: "Mental health treatment that feels genuinely personal", highlight: true },
    { name: "Evidence-Based Practice", desc: "NYU teaching credibility meets clinical excellence", highlight: true },
    { name: "Integrated Approach", desc: "Psychiatry and psychotherapy working together", highlight: true },
    { name: "Responsive Design", desc: "Care that adapts to your unique needs", highlight: false },
    { name: "High-Achiever Focus", desc: "Understanding perfectionism and professional demands", highlight: false }
  ];
  let carousel: HTMLElement;

  import { onMount } from 'svelte';
  
  onMount(() => {
    if (carousel) {
      const centerImage = carousel.children[1] as HTMLElement;
      if (centerImage) {
        const scrollLeft = centerImage.offsetLeft - (carousel.clientWidth - centerImage.clientWidth) / 2;
        carousel.scrollLeft = scrollLeft;
      }
    }
  });
</script>

<Header />

<main class="pt-32 pb-20 px-5 md:px-10 font-sans text-black selection:bg-gray-200">
  
  <!-- Hero Headline -->
  <div class="mb-20 md:mb-32 max-w-5xl">
    <h1 class="text-4xl md:text-6xl lg:text-7xl leading-[1.1] font-normal tracking-tight">
      Personalized mental wellness through integrated psychiatry, psychotherapy, and human-centered care.
    </h1>
  </div>

  <!-- Hero Carousel -->
  <div class="mb-32 relative -mx-5 md:-mx-10">
    <div bind:this={carousel} class="flex gap-4 md:gap-8 overflow-x-auto pb-8 snap-x snap-mandatory scrollbar-hide px-5 md:px-10">
      <!-- Left Image (Partial) -->
      <div class="shrink-0 w-[80vw] md:w-[60vw] lg:w-[40vw] snap-center opacity-50 transition-all hover:opacity-100">
        <img src="/generated/image-confident-professional-woman-in-her-30s--1765660972311-1.webp" alt="NYC Professional" class="w-full h-[400px] md:h-[600px] object-cover" />
      </div>
      
      <!-- Center Image (Main) -->
      <div class="shrink-0 w-[90vw] md:w-[70vw] lg:w-[50vw] snap-center relative">
        <img src="/generated/image-professional-therapists-office-in-nyc-wi-1765660969719-0.webp" alt="Light Room Therapy Space" class="w-full h-[400px] md:h-[600px] object-cover" />
        <div class="mt-4">
          <h3 class="text-lg font-medium">A Space for Healing</h3>
          <p class="text-gray-500 text-lg">Warm, welcoming environment designed for your comfort</p>
        </div>
      </div>

      <!-- Right Image (Partial) -->
      <div class="shrink-0 w-[80vw] md:w-[60vw] lg:w-[40vw] snap-center opacity-50 transition-all hover:opacity-100">
        <img src="/generated/image-peaceful-therapy-session-with-psychiatri-1765660974421-2.webp" alt="Therapy Session" class="w-full h-[400px] md:h-[600px] object-cover" />
      </div>
       <!-- Extra Image -->
       <div class="shrink-0 w-[80vw] md:w-[60vw] lg:w-[40vw] snap-center opacity-50 transition-all hover:opacity-100">
        <img src="/generated/image-nyc-professional-man-in-business-casual--1765660976548-3.webp" alt="Professional seeking care" class="w-full h-[400px] md:h-[600px] object-cover" />
      </div>
    </div>
  </div>

  <!-- Services -->
  <Section label="Our Services">
    <div class="flex flex-col border-t border-gray-200">
      {#each services as service}
        <a href="#contact" class="py-6 border-b border-gray-200 text-3xl md:text-4xl lg:text-5xl font-normal hover:text-gray-500 transition-colors block">
          {service}
        </a>
      {/each}
    </div>
  </Section>

  <!-- Insights & Resources -->
  <Section label="Insights & Resources" link="/" linkText="All resources">
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
      {#each insights as item}
        <article class="group cursor-pointer">
          <div class="overflow-hidden mb-4">
            <img src={item.image} alt={item.title} class="w-full aspect-[4/3] object-cover group-hover:scale-105 transition-transform duration-500" />
          </div>
          <time class="text-gray-500 text-sm block mb-2">{item.date}</time>
          <h3 class="text-xl leading-snug group-hover:underline decoration-1 underline-offset-4">{item.title}</h3>
        </article>
      {/each}
    </div>
    
    <!-- Navigation Arrows -->
    <div class="flex justify-between mt-12 border-t border-transparent">
      <button class="hover:opacity-50 transition-opacity p-2 -ml-2">
        <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
          <path d="M19 12H5M12 19l-7-7 7-7"/>
        </svg>
      </button>
      <button class="hover:opacity-50 transition-opacity p-2 -mr-2">
        <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
          <path d="M5 12h14M12 5l7 7-7 7"/>
        </svg>
      </button>
    </div>
  </Section>

  <!-- Our Approach -->
  <div class="grid grid-cols-1 md:grid-cols-2 gap-10 md:gap-20 py-20 md:py-32">
    <div>
      <img src="/generated/image-modern-psychiatrist-reviewing-notes-in-a-1765660978596-4.webp" alt="Evidence-based care" class="w-full aspect-[4/3] object-cover mb-6" />
      <h3 class="text-xl font-medium mb-2">Evidence-Based Care</h3>
      <p class="text-gray-500 text-lg leading-relaxed">
        Dr. Michael Nakhla brings NYU teaching credentials and academic medicine expertise to deliver psychiatric care grounded in the latest research and clinical best practices.
      </p>
    </div>
    <div>
      <img src="/generated/image-two-people-having-a-supportive-conversat-1765660980727-5.webp" alt="Human-centered approach" class="w-full aspect-[4/3] object-cover mb-6" />
      <h3 class="text-xl font-medium mb-2">Human-Centered Approach</h3>
      <p class="text-gray-500 text-lg leading-relaxed">
        Mental health care should never feel impersonal. We integrate psychiatry and psychotherapy in a collaborative model that puts your unique needs and experiences at the center.
      </p>
    </div>
  </div>

  <!-- Our Values -->
  <Section label="What Guides Us">
    <div class="flex flex-col gap-2">
      {#each values as value}
        <div class="group block">
          <h3 class="text-3xl md:text-5xl lg:text-6xl font-normal leading-tight">
            <span>{value.name}</span>
            {#if value.desc}
              <span class="text-gray-300 ml-2 transition-colors">{value.desc}</span>
            {/if}
          </h3>
        </div>
      {/each}
      
      <a href="#contact" class="inline-flex items-center gap-2 text-lg text-gray-500 mt-12 hover:text-black transition-colors group">
        → <span class="group-hover:translate-x-1 transition-transform">Learn more about our approach</span>
      </a>
    </div>
  </Section>

  <!-- Get Started -->
  <div id="contact" class="py-20 md:py-32">
    <div class="max-w-xl">
      <img src="/generated/image-welcoming-reception-area-of-modern-menta-1765660989652-9.webp" alt="Light Room reception" class="w-full aspect-[3/2] object-cover mb-6" />
      <h3 class="text-xl font-medium mb-2">Start Your Journey</h3>
      <p class="text-gray-500 text-lg mb-6">
        Ready to experience mental health care that feels human? We accept most major insurance plans and offer guidance on reimbursement. Located in NYC.
      </p>
      <a href="mailto:contact@lightroom.care" class="inline-flex items-center gap-3 px-6 py-3 bg-black text-white hover:bg-gray-800 transition-colors">
        Book a Consultation
        <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
          <path d="M5 12h14M12 5l7 7-7 7"/>
        </svg>
      </a>
    </div>
  </div>

  <!-- Footer -->
  <footer class="pt-20 border-t border-gray-200">
    <div class="grid grid-cols-1 md:grid-cols-12 gap-10 md:gap-4">
      <!-- Logo Column -->
      <div class="col-span-1 md:col-span-2">
        <svg width="40" height="40" viewBox="0 0 97 97" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M22.4438 10.875C22.4438 16.8811 17.6084 21.75 11.6438 21.75C5.67908 21.75 0.84375 16.8811 0.84375 10.875C0.84375 4.86891 5.67908 0 11.6438 0C17.6084 0 22.4438 4.86891 22.4438 10.875Z" fill="currentColor"/>
          <path d="M59.6439 10.875C59.6439 16.8811 54.8087 21.75 48.8439 21.75C42.8792 21.75 38.0439 16.8811 38.0439 10.875C38.0439 4.86891 42.8792 0 48.8439 0C54.8087 0 59.6439 4.86891 59.6439 10.875Z" fill="currentColor"/>
          <path d="M96.8441 10.875C96.8441 16.8811 92.0089 21.75 86.0441 21.75C80.0794 21.75 75.2441 16.8811 75.2441 10.875C75.2441 4.86891 80.0794 0 86.0441 0C92.0089 0 96.8441 4.86891 96.8441 10.875Z" fill="currentColor"/>
          <path d="M22.4438 48.3334C22.4438 54.3395 17.6084 59.2084 11.6438 59.2084C5.67908 59.2084 0.84375 54.3395 0.84375 48.3334C0.84375 42.3272 5.67908 37.4584 11.6438 37.4584C17.6084 37.4584 22.4438 42.3272 22.4438 48.3334Z" fill="currentColor"/>
          <path d="M59.6439 48.3334C59.6439 54.3395 54.8087 59.2084 48.8439 59.2084C42.8792 59.2084 38.0439 54.3395 38.0439 48.3334C38.0439 42.3272 42.8792 37.4584 48.8439 37.4584C54.8087 37.4584 59.6439 42.3272 59.6439 48.3334Z" fill="currentColor"/>
          <path d="M96.8441 48.3334C96.8441 54.3395 92.0089 59.2084 86.0441 59.2084C80.0794 59.2084 75.2441 54.3395 75.2441 48.3334C75.2441 42.3272 80.0794 37.4584 86.0441 37.4584C92.0089 37.4584 96.8441 42.3272 96.8441 48.3334Z" fill="currentColor"/>
          <path d="M22.4438 85.7917C22.4438 91.7979 17.6084 96.6667 11.6438 96.6667C5.67908 96.6667 0.84375 91.7979 0.84375 85.7917C0.84375 79.7856 5.67908 74.9167 11.6438 74.9167C17.6084 74.9167 22.4438 79.7856 22.4438 85.7917Z" fill="currentColor"/>
          <path d="M59.6439 85.7917C59.6439 91.7979 54.8087 96.6667 48.8439 96.6667C42.8792 96.6667 38.0439 91.7979 38.0439 85.7917C38.0439 79.7856 42.8792 74.9167 48.8439 74.9167C54.8087 74.9167 59.6439 79.7856 59.6439 85.7917Z" fill="currentColor"/>
          <path d="M96.8441 85.7917C96.8441 91.7979 92.0089 96.6667 86.0441 96.6667C80.0794 96.6667 75.2441 91.7979 75.2441 85.7917C75.2441 79.7856 80.0794 74.9167 86.0441 74.9167C92.0089 74.9167 96.8441 79.7856 96.8441 85.7917Z" fill="currentColor"/>
        </svg>
      </div>

      <!-- Links Columns -->
      <div class="col-span-1 md:col-span-2">
        <h4 class="text-gray-400 mb-6 text-sm">Practice</h4>
        <ul class="space-y-2 text-sm text-gray-600">
          <li><a href="#contact" class="hover:text-black">Book Consultation</a></li>
          <li><a href="/" class="hover:text-black">About Dr. Nakhla</a></li>
          <li><a href="/" class="hover:text-black">Our Approach</a></li>
          <li><a href="/" class="hover:text-black">Insurance & Fees</a></li>
          <li><a href="/" class="hover:text-black">Location</a></li>
          <li><a href="/" class="hover:text-black">FAQ</a></li>
        </ul>
      </div>

      <div class="col-span-1 md:col-span-2">
        <h4 class="text-gray-400 mb-6 text-sm">Services</h4>
        <ul class="space-y-2 text-sm text-gray-600">
          <li><a href="/" class="hover:text-black">Psychiatry</a></li>
          <li><a href="/" class="hover:text-black">Psychotherapy</a></li>
          <li><a href="/" class="hover:text-black">Medication Management</a></li>
          <li><a href="/" class="hover:text-black">Collaborative Care</a></li>
        </ul>
      </div>

      <div class="col-span-1 md:col-span-2">
        <h4 class="text-gray-400 mb-6 text-sm">Resources</h4>
        <ul class="space-y-2 text-sm text-gray-600">
          <li><a href="/" class="hover:text-black">Mental Health Insights</a></li>
          <li><a href="/" class="hover:text-black">For High Achievers</a></li>
          <li><a href="/" class="hover:text-black">Crisis Support</a></li>
        </ul>
      </div>

      <!-- Contact Info -->
      <div class="col-span-1 md:col-span-4 flex flex-col justify-end">
        <div class="text-sm text-gray-600 space-y-2">
          <p class="font-medium text-black">Light Room</p>
          <p>New York, NY</p>
          <p><a href="mailto:contact@lightroom.care" class="hover:text-black">contact@lightroom.care</a></p>
        </div>
      </div>
    </div>

    <!-- Bottom Footer -->
    <div class="mt-20 py-8 flex flex-col md:flex-row justify-between items-start md:items-center text-xs text-gray-500 gap-4">
      <div>© Light Room 2025</div>
      
      <div class="flex gap-6">
        <a href="/" class="hover:text-black">Privacy Policy</a>
        <a href="/" class="hover:text-black">HIPAA Notice</a>
        <a href="/" class="hover:text-black">Terms of Service</a>
      </div>

      <div class="flex gap-6">
        <a href="/" class="hover:text-black">LinkedIn</a>
        <a href="/" class="hover:text-black">Psychology Today</a>
      </div>
    </div>
  </footer>

</main>

