<script setup lang="ts">
const leistungen = [
  { title: 'Responsive Design', description: 'Optimale Darstellung auf allen Geräten' },
  { title: 'UX/UI Design', description: 'Benutzerfreundliche und intuitive Interfaces' },
  { title: 'E-Commerce', description: 'Leistungsstarke Online-Shops' },
  { title: 'CMS Entwicklung', description: 'Einfach zu pflegende Inhalte' },
  { title: 'Performance', description: 'Schnelle Ladezeiten und optimale Core Web Vitals' },
  { title: 'SEO', description: 'Suchmaschinenoptimierung für mehr Sichtbarkeit' },
]

const technologien = [
  'Vue.js', 'Nuxt', 'React', 'Next.js', 'TypeScript', 'Tailwind CSS', 'WordPress', 'Shopify'
]
</script>

<template>
  <div>
    <!-- Hero -->
    <section class="pt-32 pb-20 bg-gray-950">
      <UContainer>
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-16 items-center">
          <div>
            <UBadge color="orange" variant="soft" class="mb-6">Design & Performance</UBadge>
            <h1 class="text-5xl md:text-6xl font-black text-white mb-6">
              Web-<br />
              <span class="text-orange-500">design</span>
            </h1>
            <p class="text-xl text-gray-400 leading-relaxed mb-8">
              Sie möchten eine professionelle Website erstellen lassen, die nicht nur optisch begeistert, sondern auch technisch auf dem neuesten Stand ist? Als erfahrene Webdesign-Agentur aus Hannover realisieren wir individuelle Websites, die perfekt auf Ihre Zielgruppe und Unternehmensziele abgestimmt sind.
            </p>
            <UButton
              size="xl"
              color="primary"
              class="bg-orange-500 hover:bg-orange-600"
              to="/kontakt"
            >
              Projekt anfragen
              <UIcon name="i-heroicons-arrow-right" class="ml-2" />
            </UButton>
          </div>
          <div class="aspect-video bg-gradient-to-br from-orange-500/20 to-gray-800 rounded-3xl flex items-center justify-center">
            <UIcon name="i-heroicons-computer-desktop" class="w-24 h-24 text-orange-500" />
          </div>
        </div>
      </UContainer>
    </section>

    <!-- Leistungen -->
    <section class="py-24 bg-gray-900">
      <UContainer>
        <div class="text-center mb-16">
          <UBadge color="orange" variant="soft" class="mb-4">Unsere Leistungen</UBadge>
          <h2 class="text-4xl font-black text-white">Was wir bieten</h2>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
          <div
            v-for="(item, index) in leistungen"
            :key="index"
            class="p-6 bg-gray-800 rounded-2xl border border-gray-700 hover:border-orange-500/50 transition-all duration-300"
          >
            <h3 class="text-xl font-bold text-white mb-2">{{ item.title }}</h3>
            <p class="text-gray-400">{{ item.description }}</p>
          </div>
        </div>
      </UContainer>
    </section>

    <!-- Technologien -->
    <section class="py-24 bg-gray-950">
      <UContainer>
        <div class="text-center mb-16">
          <UBadge color="orange" variant="soft" class="mb-4">Unser Tech Stack</UBadge>
          <h2 class="text-4xl font-black text-white">Moderne Technologien</h2>
        </div>

        <div class="flex flex-wrap justify-center gap-4">
          <div
            v-for="(tech, index) in technologien"
            :key="index"
            class="px-6 py-3 bg-gray-900 rounded-xl border border-gray-800 text-gray-300 font-medium hover:border-orange-500/50 hover:text-orange-500 transition-all duration-300"
          >
            {{ tech }}
          </div>
        </div>
      </UContainer>
    </section>

    <!-- CTA -->
    <section class="py-24 bg-gray-900">
      <UContainer>
        <div class="text-center max-w-3xl mx-auto">
          <h2 class="text-4xl font-black text-white mb-6">
            Bereit für Ihre neue Website?
          </h2>
          <p class="text-gray-400 text-lg mb-10">
            Ob neue Website oder Optimierung einer bestehenden Seite – wir sind Ihr Partner für maßgeschneiderte digitale Lösungen.
          </p>
          <UButton
            size="xl"
            color="primary"
            class="bg-orange-500 hover:bg-orange-600"
            to="/kontakt"
          >
            Kostenloses Erstgespräch
            <UIcon name="i-heroicons-arrow-right" class="ml-2" />
          </UButton>
        </div>
      </UContainer>
    </section>
  </div>
</template>
