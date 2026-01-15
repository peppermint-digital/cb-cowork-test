<script setup lang="ts">
const leistungen = [
  { title: 'Imagefilme', description: 'Authentische Unternehmensporträts, die Ihre Marke erlebbar machen' },
  { title: 'Werbefilme', description: 'Kreative Spots für TV, Web und Social Media' },
  { title: 'Social Media Videos', description: 'Snackable Content für alle Plattformen' },
  { title: 'Employer Branding', description: 'Recruiting-Videos die Talente ansprechen' },
  { title: 'Produktvideos', description: 'Professionelle Produktpräsentationen' },
  { title: 'Eventdokumentation', description: 'Ihre Veranstaltung filmisch festgehalten' },
]

const prozess = [
  { step: '01', title: 'Konzeption', description: 'Gemeinsame Entwicklung der Story und des visuellen Konzepts' },
  { step: '02', title: 'Pre-Production', description: 'Planung, Casting, Location-Scouting und Vorbereitung' },
  { step: '03', title: 'Produktion', description: 'Professioneller Dreh mit unserem erfahrenen Team' },
  { step: '04', title: 'Post-Production', description: 'Schnitt, Color Grading, Sound Design und Finishing' },
]
</script>

<template>
  <div>
    <!-- Hero -->
    <section class="pt-32 pb-20 bg-gray-950">
      <UContainer>
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-16 items-center">
          <div>
            <UBadge color="orange" variant="soft" class="mb-6">Bewegtbild ist King</UBadge>
            <h1 class="text-5xl md:text-6xl font-black text-white mb-6">
              Film-<br />
              <span class="text-orange-500">produktion</span>
            </h1>
            <p class="text-xl text-gray-400 leading-relaxed mb-8">
              Bei Peppermint Digital gestalten wir wirkungsvolle Filme, die Ihre Marke sichtbar und erlebbar machen. Ob Imagefilm, Werbefilm, Social Media Video oder Employer-Branding-Content – wir erzählen Ihre Geschichte authentisch, emotional und mit filmischer Präzision.
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
            <UIcon name="i-heroicons-play-circle" class="w-24 h-24 text-orange-500" />
          </div>
        </div>
      </UContainer>
    </section>

    <!-- Leistungen -->
    <section class="py-24 bg-gray-900">
      <UContainer>
        <div class="text-center mb-16">
          <UBadge color="orange" variant="soft" class="mb-4">Unsere Leistungen</UBadge>
          <h2 class="text-4xl font-black text-white">Was wir produzieren</h2>
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

    <!-- Prozess -->
    <section class="py-24 bg-gray-950">
      <UContainer>
        <div class="text-center mb-16">
          <UBadge color="orange" variant="soft" class="mb-4">Von der Idee zum Film</UBadge>
          <h2 class="text-4xl font-black text-white">Unser Prozess</h2>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
          <div
            v-for="(item, index) in prozess"
            :key="index"
            class="relative"
          >
            <div class="text-6xl font-black text-orange-500/20 mb-4">{{ item.step }}</div>
            <h3 class="text-xl font-bold text-white mb-2">{{ item.title }}</h3>
            <p class="text-gray-400">{{ item.description }}</p>
          </div>
        </div>
      </UContainer>
    </section>

    <!-- CTA -->
    <section class="py-24 bg-gray-900">
      <UContainer>
        <div class="text-center max-w-3xl mx-auto">
          <h2 class="text-4xl font-black text-white mb-6">
            Lassen Sie uns Ihre Geschichte erzählen
          </h2>
          <p class="text-gray-400 text-lg mb-10">
            Unsere Filme schaffen Vertrauen, wecken Emotionen und bleiben im Kopf.
          </p>
          <div class="flex flex-col sm:flex-row gap-4 justify-center">
            <UButton
              size="xl"
              color="primary"
              class="bg-orange-500 hover:bg-orange-600"
              to="/kontakt"
            >
              Projekt starten
            </UButton>
            <UButton
              size="xl"
              variant="outline"
              color="white"
              to="/projekte"
            >
              Referenzen ansehen
            </UButton>
          </div>
        </div>
      </UContainer>
    </section>
  </div>
</template>
