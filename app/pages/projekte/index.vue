<script setup lang="ts">
// Hero image
const heroImage = 'https://peppermint-digital.de/wp-content/uploads/2024/09/peppermint-digital-success-stories.webp'

const projekte = [
  {
    title: 'PAYEASY',
    subtitle: 'Aufbau einer neuen Payment-Marke',
    category: 'Branding & Marketing',
    image: 'https://peppermint-digital.de/wp-content/uploads/2024/12/payeasy-preview.webp'
  },
  {
    title: 'AGRITECHNICA 2025',
    subtitle: 'Die größte Landwirtschaftsmesse der Welt',
    category: 'Event & Filmproduktion',
    image: 'https://peppermint-digital.de/wp-content/uploads/2024/12/agritechnica-preview.webp'
  },
  {
    title: 'R+E TODTENHAUPT GMBH & CO. KG',
    subtitle: 'Wertefilm und Website-Relaunch',
    category: 'Web & Film',
    image: 'https://peppermint-digital.de/wp-content/uploads/2024/12/todtenhaupt-preview.webp'
  },
  {
    title: 'INTERAKTIVE RECRUITING-FILME',
    subtitle: 'Für die Autohausgruppen RKG und Markötter',
    category: 'Filmproduktion',
    image: 'https://peppermint-digital.de/wp-content/uploads/2024/12/recruiting-filme-preview.webp'
  },
  {
    title: 'CARS & BYTES',
    subtitle: 'On Tour',
    category: 'Event & Content',
    image: 'https://peppermint-digital.de/wp-content/uploads/2024/10/cb-2025-website.webp'
  },
  {
    title: 'TSV HANNOVER-BURGDORF',
    subtitle: 'Sponsorentag',
    category: 'Event & Filmproduktion',
    image: 'https://peppermint-digital.de/wp-content/uploads/2024/12/tsv-preview.webp'
  }
]

const kategorien = [
  'Alle',
  'Filmproduktion',
  'Webdesign',
  'Marketing',
  'Events'
]
</script>

<template>
  <div>
    <!-- Hero -->
    <section class="relative min-h-[70vh] flex items-center justify-center overflow-hidden">
      <!-- Background Image -->
      <div class="absolute inset-0">
        <img
          :src="heroImage"
          alt="Success Stories"
          class="absolute inset-0 w-full h-full object-cover"
        />
        <div class="absolute inset-0 bg-black/50" />
      </div>
      <UContainer class="relative">
        <div class="text-center max-w-4xl mx-auto">
          <UBadge color="orange" variant="soft" class="mb-6">Unsere Arbeit</UBadge>
          <h1 class="text-5xl md:text-7xl font-black text-white mb-6">
            Success<br />
            <span class="text-orange-500">Stories</span>
          </h1>
          <p class="text-xl text-gray-400 leading-relaxed max-w-2xl mx-auto">
            Hier finden Sie einen Auszug über unsere erfolgreich abgeschlossenen Projekte, die unser Engagement und unsere Expertise in den Bereichen Marketing, Videoproduktion, Softwareentwicklung und mehr demonstrieren.
          </p>
        </div>
      </UContainer>
    </section>

    <!-- Intro -->
    <section class="py-16 bg-gray-900">
      <UContainer>
        <div class="flex flex-col md:flex-row md:items-end md:justify-between gap-8">
          <div>
            <UBadge color="orange" variant="soft" class="mb-4">Die wir schreiben</UBadge>
            <h2 class="text-4xl font-black text-white">Erfolgsgeschichte</h2>
          </div>
          <div class="flex flex-wrap gap-2">
            <UButton
              v-for="kategorie in kategorien"
              :key="kategorie"
              size="sm"
              :color="kategorie === 'Alle' ? 'primary' : 'neutral'"
              :variant="kategorie === 'Alle' ? 'solid' : 'outline'"
              :class="kategorie === 'Alle' ? 'bg-orange-500 hover:bg-orange-600' : 'border-gray-700 text-gray-400 hover:border-orange-500 hover:text-orange-500'"
            >
              {{ kategorie }}
            </UButton>
          </div>
        </div>
      </UContainer>
    </section>

    <!-- Projects Grid -->
    <section class="py-16 bg-gray-950">
      <UContainer>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
          <div
            v-for="(projekt, index) in projekte"
            :key="index"
            class="group relative aspect-[4/3] bg-gray-900 rounded-2xl overflow-hidden cursor-pointer"
          >
            <!-- Background Image -->
            <img
              :src="projekt.image"
              :alt="projekt.title"
              class="absolute inset-0 w-full h-full object-cover transition-transform duration-500 group-hover:scale-110"
            />

            <!-- Overlay -->
            <div class="absolute inset-0 bg-gradient-to-t from-black/90 via-black/30 to-transparent group-hover:from-black/80 transition-all duration-300" />

            <!-- Text content -->
            <div class="absolute bottom-0 left-0 right-0 p-6">
              <span class="text-orange-500 text-sm font-medium mb-2 block">{{ projekt.category }}</span>
              <h3 class="text-2xl font-black text-orange-500 mb-1">{{ projekt.title }}</h3>
              <p class="text-gray-300">{{ projekt.subtitle }}</p>
            </div>

            <!-- Hover effect -->
            <div class="absolute inset-0 border-2 border-transparent group-hover:border-orange-500/50 rounded-2xl transition-all duration-300" />
          </div>
        </div>
      </UContainer>
    </section>

    <!-- Stats -->
    <section class="py-24 bg-gray-900">
      <UContainer>
        <div class="grid grid-cols-2 md:grid-cols-4 gap-8">
          <div class="text-center">
            <div class="text-5xl font-black text-orange-500 mb-2">250+</div>
            <div class="text-gray-400">Kooperationen</div>
          </div>
          <div class="text-center">
            <div class="text-5xl font-black text-orange-500 mb-2">102k</div>
            <div class="text-gray-400">Filmminuten</div>
          </div>
          <div class="text-center">
            <div class="text-5xl font-black text-orange-500 mb-2">20+</div>
            <div class="text-gray-400">Mitarbeiter</div>
          </div>
          <div class="text-center">
            <div class="text-5xl font-black text-orange-500 mb-2">100%</div>
            <div class="text-gray-400">Herzblut</div>
          </div>
        </div>
      </UContainer>
    </section>

    <!-- CTA -->
    <section class="py-24 bg-gray-950">
      <UContainer>
        <div class="text-center max-w-3xl mx-auto">
          <h2 class="text-4xl font-black text-white mb-6">
            Ihr Projekt. Unsere Expertise.
          </h2>
          <p class="text-gray-400 text-lg mb-10">
            Lassen Sie uns gemeinsam Ihre nächste Success Story schreiben. Von der ersten Idee bis zur finalen Umsetzung – wir begleiten Sie auf dem Weg zum Erfolg.
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
      </UContainer>
    </section>
  </div>
</template>
