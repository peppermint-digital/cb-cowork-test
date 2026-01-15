<script setup lang="ts">
// Stats animation
const stats = ref([
  { value: 0, target: 250, suffix: '+', label: 'Erfolgreiche Kooperationen' },
  { value: 0, target: 102, suffix: 'k', label: 'Filmminuten produziert' },
  { value: 0, target: 20, suffix: '+', label: 'Team-Mitglieder' },
  { value: 0, target: 100, suffix: '%', label: 'Herzblut' }
])

const statsVisible = ref(false)
const statsSection = ref<HTMLElement | null>(null)

onMounted(() => {
  const observer = new IntersectionObserver(([entry]) => {
    if (entry.isIntersecting && !statsVisible.value) {
      statsVisible.value = true
      animateStats()
      observer.unobserve(entry.target)
    }
  }, { threshold: 0.3 })

  if (statsSection.value) {
    observer.observe(statsSection.value)
  }
})

function animateStats() {
  stats.value.forEach((stat, index) => {
    const duration = 2000
    const steps = 60
    const increment = stat.target / steps
    let current = 0

    const interval = setInterval(() => {
      current += increment
      if (current >= stat.target) {
        stats.value[index].value = stat.target
        clearInterval(interval)
      } else {
        stats.value[index].value = Math.floor(current)
      }
    }, duration / steps)
  })
}

// Services data
const services = [
  {
    icon: 'i-heroicons-film',
    title: 'Filmproduktion',
    subtitle: 'Bewegtbild ist King',
    description: 'Wir gestalten wirkungsvolle Filme, die Ihre Marke sichtbar und erlebbar machen.',
    link: '/services/filmproduktion'
  },
  {
    icon: 'i-heroicons-globe-alt',
    title: 'Webdesign',
    subtitle: 'Design & Performance',
    description: 'Individuelle Websites, die perfekt auf Ihre Zielgruppe abgestimmt sind.',
    link: '/services/webdesign'
  },
  {
    icon: 'i-heroicons-code-bracket',
    title: 'Software Entwicklung',
    subtitle: 'Individuelle Lösungen',
    description: 'Professionelle App- und Software-Lösungen für Ihre Anforderungen.',
    link: '/services/software'
  },
  {
    icon: 'i-heroicons-megaphone',
    title: 'Social Media Marketing',
    subtitle: 'Die richtige Platzierung',
    description: 'Kreative Content-Erstellung und Performance Ads für Ihre Zielgruppe.',
    link: '/services/marketing'
  }
]

// Clients with logos
const clients = [
  { name: 'Cars & Bytes', logo: 'https://peppermint-digital.de/cb-logo.webp' },
  { name: 'Hannover 96', logo: 'https://peppermint-digital.de/logo-96.webp' },
  { name: 'Dominos', logo: 'https://peppermint-digital.de/logo-dominos.webp' },
  { name: 'Bentley', logo: 'https://peppermint-digital.de/logo-bentley.webp' },
  { name: 'TÜV Nord', logo: 'https://peppermint-digital.de/tuevnord-logo-neu-weiss.webp' },
  { name: 'TCS', logo: 'https://peppermint-digital.de/tcs-logo-weiss.webp' },
  { name: 'Mobile.de', logo: 'https://peppermint-digital.de/mobile-logo.webp' },
  { name: 'Toyota', logo: 'https://peppermint-digital.de/toyota-logo.webp' },
  { name: 'Carwow', logo: 'https://peppermint-digital.de/carwow-logo-weiss.png' },
  { name: 'McPaper', logo: 'https://peppermint-digital.de/mcpaper-logo.png' }
]

// Hero background images (rotating)
const heroImages = [
  'https://peppermint-digital.de/wp-content/uploads/2024/09/peppermint-digital-header-jungheinrich.webp',
  'https://peppermint-digital.de/wp-content/uploads/2024/09/peppermint-digital-header-intercity.webp',
  'https://peppermint-digital.de/wp-content/uploads/2024/09/peppermint-digital-header-porsche.webp'
]

const currentHeroImage = ref(0)

onMounted(() => {
  setInterval(() => {
    currentHeroImage.value = (currentHeroImage.value + 1) % heroImages.length
  }, 5000)
})

// Projects with images
const projects = [
  {
    title: 'Cars & Bytes 2025',
    category: 'Partnerakquise | Marketing | Produktion',
    description: 'Deutschlands größtes digitales Mobilitätserlebnis',
    image: 'https://peppermint-digital.de/wp-content/uploads/2024/10/cb-2025-website.webp'
  },
  {
    title: 'PAYEASY',
    category: 'Branding & Marketing',
    description: 'Aufbau einer neuen Payment-Marke',
    image: 'https://peppermint-digital.de/wp-content/uploads/2024/12/payeasy-preview.webp'
  },
  {
    title: 'Agritechnica 2025',
    category: 'Event & Filmproduktion',
    description: 'Die größte Landwirtschaftsmesse der Welt',
    image: 'https://peppermint-digital.de/wp-content/uploads/2024/12/agritechnica-preview.webp'
  }
]
</script>

<template>
  <div>
    <!-- Hero Section -->
    <section class="relative min-h-screen flex items-center justify-center overflow-hidden">
      <!-- Background Images with transition -->
      <div class="absolute inset-0">
        <div
          v-for="(image, index) in heroImages"
          :key="index"
          class="absolute inset-0 bg-cover bg-center transition-opacity duration-1000"
          :style="{ backgroundImage: `url(${image})` }"
          :class="currentHeroImage === index ? 'opacity-100' : 'opacity-0'"
        />
        <!-- Dark overlay -->
        <div class="absolute inset-0 bg-black/50" />
      </div>

      <!-- Content -->
      <UContainer class="relative z-10 text-center">
        <div class="animate-fade-in-up">
          <UBadge color="orange" variant="soft" class="mb-6 animate-bounce-slow">
            Digitalagentur aus Hannover
          </UBadge>

          <h1 class="text-5xl md:text-7xl lg:text-8xl font-black text-white mb-6 leading-tight">
            <span class="block">Digitale</span>
            <span class="block bg-gradient-to-r from-orange-400 via-orange-500 to-orange-600 bg-clip-text text-transparent">
              Problemlöser
            </span>
          </h1>

          <p class="text-xl md:text-2xl text-gray-400 max-w-3xl mx-auto mb-10">
            Peppermint Digital - Ihre Digitalagentur für Filmproduktion, Webentwicklung und maßgeschneiderte Softwarelösungen
          </p>

          <div class="flex flex-col sm:flex-row gap-4 justify-center">
            <UButton
              size="xl"
              color="primary"
              class="bg-orange-500 hover:bg-orange-600 px-8 py-4 text-lg font-semibold shadow-lg shadow-orange-500/25 hover:shadow-orange-500/40 transition-all duration-300 hover:scale-105"
              to="/kontakt"
            >
              Projekt starten
              <UIcon name="i-heroicons-arrow-right" class="ml-2" />
            </UButton>
            <UButton
              size="xl"
              variant="outline"
              color="white"
              class="px-8 py-4 text-lg font-semibold hover:bg-white/10 transition-all duration-300"
              to="/services"
            >
              Unsere Services
            </UButton>
          </div>
        </div>

        <div class="absolute bottom-10 left-1/2 transform -translate-x-1/2 animate-bounce">
          <UIcon name="i-heroicons-chevron-down" class="w-8 h-8 text-orange-500" />
        </div>
      </UContainer>
    </section>

    <!-- About Teaser -->
    <section class="py-24 bg-gray-950">
      <UContainer>
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-16 items-center">
          <div class="space-y-6">
            <UBadge color="orange" variant="soft">Das sind wir</UBadge>
            <h2 class="text-4xl md:text-5xl font-black text-white">
              Digitalagentur<br />
              <span class="text-orange-500">Hannover</span>
            </h2>
            <p class="text-gray-400 text-lg leading-relaxed">
              Wir sind eine Kreativ- und Digitalagentur aus Hannover mit Fokus auf hochwertige Filmproduktion, individuelle Webentwicklung und maßgeschneiderte Softwarelösungen.
            </p>
            <p class="text-gray-400 text-lg leading-relaxed">
              Mit eigenem Studio, Inhouse-Filmcrew und erfahrenem Entwicklerteam liefern wir kreative Inhalte und technische Lösungen aus einer Hand.
            </p>
            <UButton color="primary" variant="soft" to="/agentur">
              Mehr über uns
              <UIcon name="i-heroicons-arrow-right" class="ml-2" />
            </UButton>
          </div>

          <div class="grid grid-cols-2 gap-4">
            <div
              v-for="(feature, index) in [
                { icon: 'i-heroicons-film', title: 'Eigenes Studio', desc: 'Professionelle Filmproduktion' },
                { icon: 'i-heroicons-users', title: 'Inhouse Team', desc: 'Kreative Experten' },
                { icon: 'i-heroicons-code-bracket', title: 'Tech Stack', desc: 'Moderne Technologien' },
                { icon: 'i-heroicons-heart', title: '100% Herzblut', desc: 'In jedem Projekt' }
              ]"
              :key="index"
              class="p-6 bg-gray-900 rounded-2xl border border-gray-800 hover:border-orange-500/50 transition-all duration-300 hover:transform hover:-translate-y-1 group"
            >
              <div class="w-12 h-12 bg-orange-500/10 rounded-xl flex items-center justify-center mb-4 group-hover:bg-orange-500/20 transition-colors">
                <UIcon :name="feature.icon" class="w-6 h-6 text-orange-500" />
              </div>
              <h3 class="text-white font-semibold mb-1">{{ feature.title }}</h3>
              <p class="text-gray-500 text-sm">{{ feature.desc }}</p>
            </div>
          </div>
        </div>
      </UContainer>
    </section>

    <!-- Clients Section -->
    <section class="py-16 bg-gray-900 border-y border-gray-800">
      <UContainer>
        <div class="text-center mb-12">
          <UBadge color="orange" variant="soft" class="mb-4">Langfristige Erfolge</UBadge>
          <h2 class="text-3xl font-bold text-white">Unsere Kunden</h2>
        </div>

        <div class="relative overflow-hidden">
          <div class="flex animate-marquee space-x-12 py-4 items-center">
            <template v-for="(client, index) in [...clients, ...clients]" :key="index">
              <div class="flex-shrink-0 px-6 py-4 grayscale hover:grayscale-0 opacity-70 hover:opacity-100 transition-all duration-300">
                <img
                  :src="client.logo"
                  :alt="client.name"
                  class="h-10 w-auto object-contain"
                />
              </div>
            </template>
          </div>
        </div>
      </UContainer>
    </section>

    <!-- Services Teaser -->
    <section class="py-24 bg-gray-950">
      <UContainer>
        <div class="text-center mb-16">
          <UBadge color="orange" variant="soft" class="mb-4">Unsere Leistungen</UBadge>
          <h2 class="text-4xl md:text-5xl font-black text-white mb-4">
            Was wir für Sie tun
          </h2>
          <p class="text-gray-400 text-lg max-w-2xl mx-auto">
            Von der ersten Idee bis zur finalen Umsetzung - wir begleiten Sie durch den gesamten digitalen Prozess
          </p>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
          <NuxtLink
            v-for="(service, index) in services"
            :key="index"
            :to="service.link"
            class="group relative p-8 bg-gray-900 rounded-3xl border border-gray-800 overflow-hidden hover:border-orange-500/50 transition-all duration-500 hover:transform hover:-translate-y-2"
          >
            <div class="absolute inset-0 bg-gradient-to-br from-orange-500/5 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-500" />

            <div class="relative z-10">
              <div class="w-16 h-16 bg-orange-500/10 rounded-2xl flex items-center justify-center mb-6 group-hover:scale-110 transition-transform duration-300">
                <UIcon :name="service.icon" class="w-8 h-8 text-orange-500" />
              </div>

              <span class="text-orange-500 text-sm font-semibold uppercase tracking-wider">
                {{ service.subtitle }}
              </span>
              <h3 class="text-2xl font-bold text-white mt-2 mb-4">
                {{ service.title }}
              </h3>
              <p class="text-gray-400 leading-relaxed mb-6">
                {{ service.description }}
              </p>

              <span class="inline-flex items-center text-orange-500 font-semibold group-hover:translate-x-2 transition-transform duration-300">
                Mehr erfahren
                <UIcon name="i-heroicons-arrow-right" class="ml-2" />
              </span>
            </div>
          </NuxtLink>
        </div>

        <div class="text-center mt-12">
          <UButton size="lg" color="primary" variant="soft" to="/services">
            Alle Services ansehen
            <UIcon name="i-heroicons-arrow-right" class="ml-2" />
          </UButton>
        </div>
      </UContainer>
    </section>

    <!-- Stats Section -->
    <section ref="statsSection" class="py-24 bg-gradient-to-b from-gray-950 to-gray-900">
      <UContainer>
        <div class="text-center mb-16">
          <UBadge color="orange" variant="soft" class="mb-4">Unsere Zahlen</UBadge>
          <h2 class="text-4xl md:text-5xl font-black text-white">Peppermint Digital</h2>
        </div>

        <div class="grid grid-cols-2 md:grid-cols-4 gap-8">
          <div
            v-for="(stat, index) in stats"
            :key="index"
            class="text-center p-8 bg-gray-900/50 rounded-2xl border border-gray-800"
          >
            <div class="text-5xl md:text-6xl font-black text-orange-500 mb-2">
              {{ stat.value }}{{ stat.suffix }}
            </div>
            <p class="text-gray-400">{{ stat.label }}</p>
          </div>
        </div>
      </UContainer>
    </section>

    <!-- Projects Teaser -->
    <section class="py-24 bg-gray-900">
      <UContainer>
        <div class="text-center mb-16">
          <UBadge color="orange" variant="soft" class="mb-4">Ein Überblick</UBadge>
          <h2 class="text-4xl md:text-5xl font-black text-white mb-4">
            Aktuelle Projekte
          </h2>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
          <NuxtLink
            v-for="(project, index) in projects"
            :key="index"
            to="/projekte"
            class="group relative overflow-hidden rounded-3xl bg-gray-800 cursor-pointer"
          >
            <div class="aspect-[4/3] relative overflow-hidden">
              <img
                :src="project.image"
                :alt="project.title"
                class="absolute inset-0 w-full h-full object-cover transition-transform duration-500 group-hover:scale-110"
              />
              <div class="absolute inset-0 bg-gradient-to-t from-gray-900 via-gray-900/30 to-transparent" />
              <div class="absolute inset-0 bg-orange-500/20 opacity-0 group-hover:opacity-100 transition-opacity duration-300" />
            </div>

            <div class="absolute bottom-0 left-0 right-0 p-6">
              <span class="text-orange-500 text-sm font-semibold uppercase tracking-wider">
                {{ project.category }}
              </span>
              <h3 class="text-xl font-bold text-white mt-2">{{ project.title }}</h3>
              <p class="text-gray-400 mt-2 opacity-0 group-hover:opacity-100 transition-opacity duration-300">
                {{ project.description }}
              </p>
            </div>

            <div class="absolute top-4 right-4 w-10 h-10 bg-white/10 rounded-full flex items-center justify-center opacity-0 group-hover:opacity-100 transition-all duration-300 group-hover:bg-orange-500">
              <UIcon name="i-heroicons-arrow-up-right" class="w-5 h-5 text-white" />
            </div>
          </NuxtLink>
        </div>

        <div class="text-center mt-12">
          <UButton size="lg" color="primary" variant="soft" to="/projekte">
            Alle Projekte ansehen
            <UIcon name="i-heroicons-arrow-right" class="ml-2" />
          </UButton>
        </div>
      </UContainer>
    </section>

    <!-- CTA Section -->
    <section class="py-24 bg-gray-950">
      <UContainer>
        <div class="text-center max-w-3xl mx-auto">
          <h2 class="text-4xl md:text-5xl font-black text-white mb-6">
            Bereit für Ihr nächstes Projekt?
          </h2>
          <p class="text-gray-400 text-lg mb-10">
            Lassen Sie uns gemeinsam Ihre Vision in die Realität umsetzen. Wir freuen uns auf Ihre Anfrage!
          </p>
          <UButton
            size="xl"
            color="primary"
            class="bg-orange-500 hover:bg-orange-600 px-10 py-4 text-lg font-semibold"
            to="/kontakt"
          >
            Jetzt Kontakt aufnehmen
            <UIcon name="i-heroicons-arrow-right" class="ml-2" />
          </UButton>
        </div>
      </UContainer>
    </section>
  </div>
</template>

<style scoped>
@keyframes fade-in-up {
  from { opacity: 0; transform: translateY(30px); }
  to { opacity: 1; transform: translateY(0); }
}

@keyframes bounce-slow {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-10px); }
}

@keyframes marquee {
  0% { transform: translateX(0); }
  100% { transform: translateX(-50%); }
}

.animate-fade-in-up { animation: fade-in-up 1s ease-out forwards; }
.animate-bounce-slow { animation: bounce-slow 3s ease-in-out infinite; }
.animate-marquee { animation: marquee 20s linear infinite; }
.delay-500 { animation-delay: 500ms; }
.delay-1000 { animation-delay: 1000ms; }
</style>
