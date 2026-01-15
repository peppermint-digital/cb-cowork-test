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
  { step: '01', title: 'Konzeption', description: 'Gemeinsame Entwicklung der Story und des visuellen Konzepts', icon: 'i-heroicons-light-bulb' },
  { step: '02', title: 'Pre-Production', description: 'Planung, Casting, Location-Scouting und Vorbereitung', icon: 'i-heroicons-clipboard-document-list' },
  { step: '03', title: 'Produktion', description: 'Professioneller Dreh mit unserem erfahrenen Team', icon: 'i-heroicons-video-camera' },
  { step: '04', title: 'Post-Production', description: 'Schnitt, Color Grading, Sound Design und Finishing', icon: 'i-heroicons-scissors' },
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
    <section class="py-32 bg-gradient-to-b from-gray-950 via-gray-900 to-gray-950 overflow-hidden">
      <UContainer>
        <div class="text-center mb-20">
          <UBadge color="orange" variant="soft" class="mb-4">Von der Idee zum Film</UBadge>
          <h2 class="text-4xl md:text-5xl font-black text-white mb-4">Unser Prozess</h2>
          <p class="text-gray-400 text-lg max-w-2xl mx-auto">
            In vier Schritten verwandeln wir Ihre Vision in bewegte Bilder
          </p>
        </div>

        <!-- Process Timeline -->
        <div class="relative">
          <!-- Connecting Line (Desktop) -->
          <div class="hidden lg:block absolute top-1/2 left-[12%] right-[12%] h-px bg-gradient-to-r from-transparent via-orange-500/40 to-transparent" />

          <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6 lg:gap-4">
            <div
              v-for="(item, index) in prozess"
              :key="index"
              class="relative group flex"
            >
              <!-- Card -->
              <div class="flex flex-col bg-gray-900/80 backdrop-blur-sm rounded-2xl p-8 border border-gray-800/50 hover:border-orange-500/30 transition-all duration-500 hover:bg-gray-900 hover:shadow-xl hover:shadow-orange-500/5 w-full">
                <!-- Step Number -->
                <div class="flex items-center gap-3 mb-6">
                  <span class="text-5xl font-black text-orange-500/20 group-hover:text-orange-500/30 transition-colors">{{ item.step }}</span>
                </div>

                <!-- Icon -->
                <div class="w-12 h-12 bg-orange-500/10 rounded-xl flex items-center justify-center mb-5 group-hover:bg-orange-500/20 transition-all duration-300">
                  <UIcon :name="item.icon" class="w-6 h-6 text-orange-500" />
                </div>

                <!-- Content -->
                <h3 class="text-lg font-bold text-white mb-2">{{ item.title }}</h3>
                <p class="text-gray-500 text-sm leading-relaxed flex-grow">{{ item.description }}</p>

                <!-- Progress Indicator -->
                <div class="mt-6 pt-4 border-t border-gray-800/50">
                  <div class="flex items-center gap-2">
                    <div class="h-1 flex-grow bg-gray-800 rounded-full overflow-hidden">
                      <div
                        class="h-full bg-gradient-to-r from-orange-500 to-orange-400 rounded-full transition-all duration-500 group-hover:w-full"
                        :style="{ width: `${(index + 1) * 25}%` }"
                      />
                    </div>
                    <span class="text-xs text-gray-600 font-medium">{{ (index + 1) * 25 }}%</span>
                  </div>
                </div>
              </div>
            </div>
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
