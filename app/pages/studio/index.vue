<script setup lang="ts">
// Studio images from original site
const studioImages = {
  hero: 'https://peppermint-digital.de/wp-content/uploads/2024/06/werkstattstudio-header.webp',
  intro: 'https://peppermint-digital.de/wp-content/uploads/2024/06/werkstattstudio-filmstudio-hannover.webp',
  production: 'https://peppermint-digital.de/wp-content/uploads/2024/06/werkstattstudio-filmproduktion.webp'
}

const features = [
  {
    title: 'Videoproduktion',
    description: 'Professionelle Filmproduktionen in unserem vollausgestatteten Studio'
  },
  {
    title: 'Fotoshootings',
    description: 'Perfekte Lichtverhältnisse für Ihre Produktfotografie'
  },
  {
    title: 'Livestreams',
    description: 'Technisch einwandfreie Live-Übertragungen für Ihre Events'
  },
  {
    title: 'Corporate Events',
    description: 'Ideale Location für Workshops, Schulungen und Präsentationen'
  },
  {
    title: 'Markeninszenierung',
    description: 'Ihre Corporate Identity perfekt in Szene gesetzt'
  },
  {
    title: 'Eventlocation',
    description: 'Flexibel nutzbar für unterschiedlichste Veranstaltungen'
  }
]

const stats = [
  { value: '425', label: 'qm Studiofläche' },
  { value: 'RGB', label: 'Studiobeleuchtung' },
  { value: '100%', label: 'Flexibilität' },
  { value: '24/7', label: 'Einsatzbereit' }
]
</script>

<template>
  <div>
    <!-- Hero -->
    <section class="relative min-h-[80vh] flex items-center justify-center overflow-hidden">
      <!-- Background Image -->
      <div class="absolute inset-0">
        <img
          :src="studioImages.hero"
          alt="Werkstattstudio Hannover"
          class="absolute inset-0 w-full h-full object-cover"
        />
        <div class="absolute inset-0 bg-black/50" />
      </div>
      <UContainer class="relative z-10">
        <div class="text-center max-w-4xl mx-auto">
          <UBadge color="orange" variant="soft" class="mb-6">Werkstattstudio Hannover</UBadge>
          <h1 class="text-5xl md:text-7xl font-black text-white mb-6">
            Filmstudio<br />
            <span class="text-orange-500">Hannover</span>
          </h1>
          <p class="text-xl text-gray-300 leading-relaxed mb-8 max-w-2xl mx-auto">
            Unser 425 qm großes Werkstattstudio in Hannover/Langenhagen ist ein flexibel nutzbarer Raum für professionelle Produktionen und kreative Formate.
          </p>
          <UButton
            size="xl"
            color="primary"
            class="bg-orange-500 hover:bg-orange-600"
            to="/kontakt"
          >
            Jetzt anfragen
            <UIcon name="i-heroicons-arrow-right" class="ml-2" />
          </UButton>
        </div>
      </UContainer>
    </section>

    <!-- Intro -->
    <section class="py-24 bg-gray-900">
      <UContainer>
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-16 items-center">
          <div>
            <UBadge color="orange" variant="soft" class="mb-4">Ihr Bedarf im Fokus</UBadge>
            <h2 class="text-4xl font-black text-white mb-6">Unser Filmstudio</h2>
            <p class="text-gray-400 text-lg leading-relaxed mb-6">
              Ob als Filmstudio, Fotostudio oder Eventfläche – die voll ausgestattete Studiofläche bietet die ideale Umgebung für vielfältige Einsätze.
            </p>
            <p class="text-gray-400 text-lg leading-relaxed">
              Mit moderner Ausstattung und offener Raumstruktur eignet sich das Studio für unterschiedlichste Anwendungen: von Videoproduktion und Fotoshootings über Workshops und Schulungen bis hin zu Markeninszenierungen und digitalen Kommunikationsformaten.
            </p>
          </div>
          <div class="aspect-video rounded-3xl overflow-hidden">
            <img
              :src="studioImages.intro"
              alt="Filmstudio Hannover"
              class="w-full h-full object-cover"
            />
          </div>
        </div>
      </UContainer>
    </section>

    <!-- Problem/Solution -->
    <section class="py-24 bg-gray-950">
      <UContainer>
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-16 items-center">
          <div class="aspect-square bg-gradient-to-br from-gray-800 to-gray-900 rounded-3xl flex items-center justify-center">
            <UIcon name="i-heroicons-light-bulb" class="w-32 h-32 text-orange-500" />
          </div>
          <div>
            <UBadge color="orange" variant="soft" class="mb-4">Für Ihre Filmproduktion</UBadge>
            <h2 class="text-4xl font-black text-white mb-8">Modernes Studio</h2>

            <div class="space-y-4 mb-8">
              <div class="flex items-start gap-4">
                <UIcon name="i-heroicons-exclamation-circle" class="w-6 h-6 text-orange-500 mt-1 flex-shrink-0" />
                <p class="text-gray-400">Keine passende Location für Ihre Film- oder Contentproduktion?</p>
              </div>
              <div class="flex items-start gap-4">
                <UIcon name="i-heroicons-exclamation-circle" class="w-6 h-6 text-orange-500 mt-1 flex-shrink-0" />
                <p class="text-gray-400">Studio zu klein oder technisch veraltet?</p>
              </div>
              <div class="flex items-start gap-4">
                <UIcon name="i-heroicons-exclamation-circle" class="w-6 h-6 text-orange-500 mt-1 flex-shrink-0" />
                <p class="text-gray-400">Kein Raum, der CI, Atmosphäre & Flexibilität miteinander verbindet?</p>
              </div>
              <div class="flex items-start gap-4">
                <UIcon name="i-heroicons-exclamation-circle" class="w-6 h-6 text-orange-500 mt-1 flex-shrink-0" />
                <p class="text-gray-400">Komplexe Produktionen lassen sich nur mit viel Eigenaufwand umsetzen?</p>
              </div>
            </div>

            <p class="text-white text-lg font-semibold mb-6">
              Wir bieten Ihnen ein modernes, wandelbares Studio mit kompletter Ausstattung – bereit für Content, Markeninszenierung & Events.
            </p>

            <UButton
              size="xl"
              color="primary"
              class="bg-orange-500 hover:bg-orange-600"
              to="/kontakt"
            >
              Jetzt anfragen
              <UIcon name="i-heroicons-arrow-right" class="ml-2" />
            </UButton>
          </div>
        </div>
      </UContainer>
    </section>

    <!-- Easy Brandfit -->
    <section class="py-24 bg-gray-900">
      <UContainer>
        <div class="text-center mb-16">
          <UBadge color="orange" variant="soft" class="mb-4">Stets Einsatzbereit</UBadge>
          <h2 class="text-4xl font-black text-white mb-6">Easy Brandfit</h2>
          <p class="text-gray-400 text-lg max-w-3xl mx-auto">
            Unser Studio in Hannover/Langenhagen ist jederzeit schnell einsatzbereit und lässt sich flexibel auf Ihre Anforderungen abstimmen. Dank individuell steuerbarer Studiobeleuchtung in RGB-Farben schaffen Sie exakt die Lichtstimmung, die zu Ihrer Marke und Ihrem Content passt.
          </p>
        </div>

        <!-- Stats -->
        <div class="grid grid-cols-2 md:grid-cols-4 gap-8 mb-16">
          <div
            v-for="(stat, index) in stats"
            :key="index"
            class="text-center p-6 bg-gray-800 rounded-2xl"
          >
            <div class="text-4xl font-black text-orange-500 mb-2">{{ stat.value }}</div>
            <div class="text-gray-400">{{ stat.label }}</div>
          </div>
        </div>
      </UContainer>
    </section>

    <!-- Features -->
    <section class="py-24 bg-gray-950">
      <UContainer>
        <div class="text-center mb-16">
          <UBadge color="orange" variant="soft" class="mb-4">Vielseitig einsetzbar</UBadge>
          <h2 class="text-4xl font-black text-white">Unsere Möglichkeiten</h2>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
          <div
            v-for="(feature, index) in features"
            :key="index"
            class="p-6 bg-gray-900 rounded-2xl border border-gray-800 hover:border-orange-500/50 transition-all duration-300"
          >
            <h3 class="text-xl font-bold text-white mb-2">{{ feature.title }}</h3>
            <p class="text-gray-400">{{ feature.description }}</p>
          </div>
        </div>
      </UContainer>
    </section>

    <!-- CTA -->
    <section class="py-24 bg-gray-900">
      <UContainer>
        <div class="text-center max-w-3xl mx-auto">
          <h2 class="text-4xl font-black text-white mb-6">
            Ihr Projekt im Werkstattstudio
          </h2>
          <p class="text-gray-400 text-lg mb-10">
            Ob Videoproduktion, Fotoshootings oder Corporate Events – mit unseren vielseitigen Lichtkonzepten und Ausstattungsmöglichkeiten wird Ihre Corporate Identity optimal in Szene gesetzt.
          </p>
          <UButton
            size="xl"
            color="primary"
            class="bg-orange-500 hover:bg-orange-600"
            to="/kontakt"
          >
            Studio anfragen
            <UIcon name="i-heroicons-arrow-right" class="ml-2" />
          </UButton>
        </div>
      </UContainer>
    </section>
  </div>
</template>
