<script setup lang="ts">
// Hero image from original site
const heroImage = 'https://peppermint-digital.de/header-agentur.webp'

// Team members with images from original site
const team = [
  { name: 'Volker Tolksdorf', role: 'Geschäftsführer', image: 'https://peppermint-digital.de/teambilder/volker-tolksdorf.webp' },
  { name: 'Roman Jordan', role: 'Geschäftsführer', image: 'https://peppermint-digital.de/teambilder/roman-jordan.webp' },
  { name: 'Chris Tolksdorf', role: 'Prokurist', image: 'https://peppermint-digital.de/teambilder/chris-tolksdorf.webp' },
  { name: 'Sarah Kurzidim', role: 'Buchhaltung', image: 'https://peppermint-digital.de/teambilder/sarah.webp' },
  { name: 'Bastian Henneberg', role: 'Head of Development', image: 'https://peppermint-digital.de/teambilder/bastian-henneberg.webp' },
  { name: 'Pauline Weber', role: 'Mediengestalterin', image: 'https://peppermint-digital.de/teambilder/pauline-gottschalk.webp' },
  { name: 'Mika Lehr', role: '3D Artist & Video-Operator', image: 'https://peppermint-digital.de/teambilder/mika-lehr.webp' },
  { name: 'Klaus Henneberg', role: 'Produktion', image: 'https://peppermint-digital.de/teambilder/klaus-henneberg.webp' },
]

const values = [
  { icon: 'i-heroicons-light-bulb', title: 'Innovation', description: 'Wir denken voraus und setzen auf modernste Technologien und kreative Ansätze.' },
  { icon: 'i-heroicons-users', title: 'Teamwork', description: 'Gemeinsam erreichen wir mehr. Wir arbeiten eng mit unseren Kunden zusammen.' },
  { icon: 'i-heroicons-check-badge', title: 'Qualität', description: 'Höchste Standards in allem was wir tun - von der Idee bis zur Umsetzung.' },
  { icon: 'i-heroicons-heart', title: 'Leidenschaft', description: '100% Herzblut in jedem Projekt. Wir lieben was wir tun.' },
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
          alt="Peppermint Digital Team"
          class="absolute inset-0 w-full h-full object-cover"
        />
        <div class="absolute inset-0 bg-black/60" />
      </div>
      <UContainer class="relative z-10">
        <div class="text-center max-w-4xl mx-auto">
          <UBadge color="orange" variant="soft" class="mb-6">Das sind wir!</UBadge>
          <h1 class="text-5xl md:text-7xl font-black text-white mb-6">
            Digitalagentur<br />
            <span class="text-orange-500">Hannover</span>
          </h1>
          <p class="text-xl text-gray-300 leading-relaxed max-w-2xl mx-auto">
            Peppermint Digital – Ihre Digitalagentur aus Hannover
          </p>
        </div>
      </UContainer>
    </section>

    <!-- Mission -->
    <section class="py-24 bg-gray-900">
      <UContainer>
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-16 items-center">
          <div>
            <UBadge color="orange" variant="soft" class="mb-6">Unsere Mission</UBadge>
            <h2 class="text-4xl font-black text-white mb-6">
              Kreative Inhalte und technische Lösungen aus einer Hand
            </h2>
            <p class="text-gray-400 text-lg leading-relaxed mb-6">
              Mit eigenem Studio, Inhouse-Filmcrew und erfahrenem Entwicklerteam liefern wir kreative Inhalte und technische Lösungen aus einer Hand – visuell stark, funktional durchdacht und immer markenorientiert.
            </p>
            <p class="text-gray-400 text-lg leading-relaxed">
              Unser Ziel ist es, Ihre Marke sichtbar und erlebbar zu machen. Dabei setzen wir auf Kreativität, modernste Technologien und enge Zusammenarbeit mit unseren Kunden.
            </p>
          </div>
          <div class="grid grid-cols-2 gap-4">
            <div class="aspect-square bg-gradient-to-br from-orange-500/20 to-gray-800 rounded-2xl flex items-center justify-center">
              <UIcon name="i-heroicons-film" class="w-16 h-16 text-orange-500" />
            </div>
            <div class="aspect-square bg-gradient-to-br from-gray-800 to-orange-500/10 rounded-2xl flex items-center justify-center mt-8">
              <UIcon name="i-heroicons-code-bracket" class="w-16 h-16 text-orange-500" />
            </div>
            <div class="aspect-square bg-gradient-to-br from-gray-800 to-orange-500/10 rounded-2xl flex items-center justify-center">
              <UIcon name="i-heroicons-paint-brush" class="w-16 h-16 text-orange-500" />
            </div>
            <div class="aspect-square bg-gradient-to-br from-orange-500/20 to-gray-800 rounded-2xl flex items-center justify-center mt-8">
              <UIcon name="i-heroicons-megaphone" class="w-16 h-16 text-orange-500" />
            </div>
          </div>
        </div>
      </UContainer>
    </section>

    <!-- Values -->
    <section class="py-24 bg-gray-950">
      <UContainer>
        <div class="text-center mb-16">
          <UBadge color="orange" variant="soft" class="mb-4">Unsere Werte</UBadge>
          <h2 class="text-4xl font-black text-white">Wofür wir stehen</h2>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
          <div
            v-for="(value, index) in values"
            :key="index"
            class="p-6 bg-gray-900 rounded-2xl border border-gray-800 hover:border-orange-500/50 transition-all duration-300 text-center group"
          >
            <div class="w-16 h-16 bg-orange-500/10 rounded-2xl flex items-center justify-center mx-auto mb-6 group-hover:bg-orange-500/20 transition-colors">
              <UIcon :name="value.icon" class="w-8 h-8 text-orange-500" />
            </div>
            <h3 class="text-xl font-bold text-white mb-3">{{ value.title }}</h3>
            <p class="text-gray-400">{{ value.description }}</p>
          </div>
        </div>
      </UContainer>
    </section>

    <!-- Team -->
    <section class="py-24 bg-gray-900">
      <UContainer>
        <div class="text-center mb-16">
          <UBadge color="orange" variant="soft" class="mb-4">Unser Team</UBadge>
          <h2 class="text-4xl font-black text-white mb-4">Die Menschen hinter Peppermint</h2>
          <p class="text-gray-400 text-lg max-w-2xl mx-auto">
            Unsere Digitalagentur besteht aktuell aus einem festen Team von 20 Personen. Vom Grafikdesigner über Software-Entwickler bis zum Videografen – diese kompetenten Menschen stecken hinter dem #teampeppermint.
          </p>
        </div>

        <div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-8">
          <div
            v-for="(member, index) in team"
            :key="index"
            class="group text-center"
          >
            <div class="aspect-square bg-gradient-to-br from-orange-100 to-orange-200 rounded-3xl mb-4 overflow-hidden group-hover:ring-4 group-hover:ring-orange-500/50 transition-all duration-300">
              <img
                :src="member.image"
                :alt="member.name"
                class="w-full h-full object-cover"
              />
            </div>
            <h3 class="text-orange-500 font-bold text-lg">{{ member.name }}</h3>
            <p class="text-gray-400 text-sm">{{ member.role }}</p>
          </div>
        </div>
      </UContainer>
    </section>

    <!-- CTA -->
    <section class="py-24 bg-gray-950">
      <UContainer>
        <div class="text-center max-w-3xl mx-auto">
          <h2 class="text-4xl font-black text-white mb-6">
            Lassen Sie uns zusammenarbeiten
          </h2>
          <p class="text-gray-400 text-lg mb-10">
            Sie haben ein Projekt im Kopf? Wir freuen uns darauf, Sie kennenzulernen!
          </p>
          <UButton
            size="xl"
            color="primary"
            class="bg-orange-500 hover:bg-orange-600"
            to="/kontakt"
          >
            Kontakt aufnehmen
            <UIcon name="i-heroicons-arrow-right" class="ml-2" />
          </UButton>
        </div>
      </UContainer>
    </section>
  </div>
</template>
