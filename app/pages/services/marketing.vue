<script setup lang="ts">
const leistungen = [
  { title: 'Content Creation', description: 'Kreativer Content für alle Social-Media-Plattformen' },
  { title: 'Performance Ads', description: 'Zielgerichtete Werbekampagnen mit messbaren Ergebnissen' },
  { title: 'Community Management', description: 'Aufbau und Pflege Ihrer Online-Community' },
  { title: 'Influencer Marketing', description: 'Strategische Kooperationen mit Influencern' },
  { title: 'Analytics & Reporting', description: 'Datenbasierte Optimierung Ihrer Kampagnen' },
  { title: 'Strategie & Beratung', description: 'Individuelle Social-Media-Strategien' },
]

const plattformen = [
  'Facebook', 'Instagram', 'LinkedIn', 'TikTok', 'YouTube', 'X (Twitter)'
]
</script>

<template>
  <div>
    <!-- Hero -->
    <section class="pt-32 pb-20 bg-gray-950">
      <UContainer>
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-16 items-center">
          <div>
            <UBadge color="orange" variant="soft" class="mb-6">Die richtige Platzierung</UBadge>
            <h1 class="text-5xl md:text-6xl font-black text-white mb-6">
              Social Media<br />
              <span class="text-orange-500">Marketing</span>
            </h1>
            <p class="text-xl text-gray-400 leading-relaxed mb-8">
              Durch kreative Content-Erstellung, gezielte Performance Ads und individuell zugeschnittene Social Media Strategien platzieren wir Ihr Unternehmen und Ihre Produkte dort, wo Ihre Zielgruppe aktiv ist.
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
            <UIcon name="i-heroicons-megaphone" class="w-24 h-24 text-orange-500" />
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

    <!-- Plattformen -->
    <section class="py-24 bg-gray-950">
      <UContainer>
        <div class="text-center mb-16">
          <UBadge color="orange" variant="soft" class="mb-4">Unsere Kanäle</UBadge>
          <h2 class="text-4xl font-black text-white">Plattformen</h2>
        </div>

        <div class="flex flex-wrap justify-center gap-4">
          <div
            v-for="(plattform, index) in plattformen"
            :key="index"
            class="px-6 py-3 bg-gray-900 rounded-xl border border-gray-800 text-gray-300 font-medium hover:border-orange-500/50 hover:text-orange-500 transition-all duration-300"
          >
            {{ plattform }}
          </div>
        </div>
      </UContainer>
    </section>

    <!-- CTA -->
    <section class="py-24 bg-gray-900">
      <UContainer>
        <div class="text-center max-w-3xl mx-auto">
          <h2 class="text-4xl font-black text-white mb-6">
            Steigern Sie Ihre Reichweite
          </h2>
          <p class="text-gray-400 text-lg mb-10">
            Ob Facebook, Instagram, LinkedIn oder TikTok – wir sorgen für eine starke Markenpräsenz in den sozialen Netzwerken.
          </p>
          <UButton
            size="xl"
            color="primary"
            class="bg-orange-500 hover:bg-orange-600"
            to="/kontakt"
          >
            Strategie besprechen
            <UIcon name="i-heroicons-arrow-right" class="ml-2" />
          </UButton>
        </div>
      </UContainer>
    </section>
  </div>
</template>
