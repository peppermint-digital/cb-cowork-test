<script setup lang="ts">
const services = [
  {
    icon: 'i-heroicons-film',
    title: 'Filmproduktion',
    subtitle: 'Bewegtbild ist King',
    description: 'Bei Peppermint Digital gestalten wir wirkungsvolle Filme, die Ihre Marke sichtbar und erlebbar machen. Ob Imagefilm, Werbefilm, Social Media Video oder Employer-Branding-Content – wir erzählen Ihre Geschichte authentisch, emotional und mit filmischer Präzision.',
    features: ['Imagefilme', 'Werbefilme', 'Social Media Videos', 'Employer Branding', 'Produktvideos', 'Eventdokumentation'],
    link: '/services/filmproduktion'
  },
  {
    icon: 'i-heroicons-globe-alt',
    title: 'Webdesign',
    subtitle: 'Design & Performance',
    description: 'Sie möchten eine professionelle Website erstellen lassen, die nicht nur optisch begeistert, sondern auch technisch auf dem neuesten Stand ist? Als erfahrene Webdesign-Agentur aus Hannover realisieren wir individuelle Websites.',
    features: ['Responsive Design', 'UX/UI Design', 'E-Commerce', 'CMS Entwicklung', 'Performance Optimierung', 'SEO'],
    link: '/services/webdesign'
  },
  {
    icon: 'i-heroicons-code-bracket',
    title: 'Software Entwicklung',
    subtitle: 'Individuelle Lösungen',
    description: 'Digitalisierung von Prozessen, Automatisierung von Abläufen oder Vereinheitlichung von unterschiedlichen Services. Wir entwickeln professionelle App- und Software-Lösungen für Sie, Ihre Kunden und Partner.',
    features: ['Web Apps', 'Mobile Apps', 'API Entwicklung', 'Datenbanken', 'Cloud Solutions', 'Automatisierung'],
    link: '/services/software'
  },
  {
    icon: 'i-heroicons-megaphone',
    title: 'Social Media Marketing',
    subtitle: 'Die richtige Platzierung',
    description: 'Durch kreative Content-Erstellung, gezielte Performance Ads und individuell zugeschnittene Social Media Strategien platzieren wir Ihr Unternehmen und Ihre Produkte dort, wo Ihre Zielgruppe aktiv ist.',
    features: ['Content Creation', 'Performance Ads', 'Community Management', 'Influencer Marketing', 'Analytics', 'Strategie'],
    link: '/services/marketing'
  }
]
</script>

<template>
  <div>
    <!-- Hero -->
    <section class="pt-32 pb-20 bg-gray-950">
      <UContainer>
        <div class="max-w-4xl">
          <UBadge color="orange" variant="soft" class="mb-6">Unsere Leistungen</UBadge>
          <h1 class="text-5xl md:text-6xl font-black text-white mb-6">
            Was wir für<br />
            <span class="text-orange-500">Sie tun</span>
          </h1>
          <p class="text-xl text-gray-400 leading-relaxed">
            Von der ersten Idee bis zur finalen Umsetzung – wir begleiten Sie durch den gesamten digitalen Prozess. Entdecken Sie unsere Services und finden Sie die perfekte Lösung für Ihr Projekt.
          </p>
        </div>
      </UContainer>
    </section>

    <!-- Services -->
    <section class="py-24 bg-gray-900">
      <UContainer>
        <div class="space-y-16">
          <NuxtLink
            v-for="(service, index) in services"
            :key="index"
            :to="service.link"
            class="block group"
          >
            <div
              class="grid grid-cols-1 lg:grid-cols-2 gap-12 p-8 bg-gray-800/50 rounded-3xl border border-gray-700 hover:border-orange-500/50 transition-all duration-300"
              :class="index % 2 === 1 ? 'lg:flex-row-reverse' : ''"
            >
              <div :class="index % 2 === 1 ? 'lg:order-2' : ''">
                <div class="flex items-center gap-4 mb-6">
                  <div class="w-16 h-16 bg-orange-500/10 rounded-2xl flex items-center justify-center group-hover:bg-orange-500/20 transition-colors">
                    <UIcon :name="service.icon" class="w-8 h-8 text-orange-500" />
                  </div>
                  <div>
                    <span class="text-orange-500 text-sm font-semibold uppercase tracking-wider">
                      {{ service.subtitle }}
                    </span>
                    <h2 class="text-3xl font-bold text-white">{{ service.title }}</h2>
                  </div>
                </div>
                <p class="text-gray-400 text-lg leading-relaxed mb-6">
                  {{ service.description }}
                </p>
                <span class="inline-flex items-center text-orange-500 font-semibold group-hover:translate-x-2 transition-transform duration-300">
                  Mehr erfahren
                  <UIcon name="i-heroicons-arrow-right" class="ml-2" />
                </span>
              </div>

              <div :class="index % 2 === 1 ? 'lg:order-1' : ''">
                <div class="grid grid-cols-2 gap-3">
                  <div
                    v-for="(feature, fIndex) in service.features"
                    :key="fIndex"
                    class="p-4 bg-gray-900/50 rounded-xl border border-gray-700 text-center"
                  >
                    <span class="text-gray-300 font-medium">{{ feature }}</span>
                  </div>
                </div>
              </div>
            </div>
          </NuxtLink>
        </div>
      </UContainer>
    </section>

    <!-- CTA -->
    <section class="py-24 bg-gray-950">
      <UContainer>
        <div class="text-center max-w-3xl mx-auto">
          <h2 class="text-4xl font-black text-white mb-6">
            Nicht sicher, welcher Service der richtige ist?
          </h2>
          <p class="text-gray-400 text-lg mb-10">
            Kein Problem! Kontaktieren Sie uns und wir finden gemeinsam die perfekte Lösung für Ihr Projekt.
          </p>
          <UButton
            size="xl"
            color="primary"
            class="bg-orange-500 hover:bg-orange-600"
            to="/kontakt"
          >
            Kostenlose Beratung
            <UIcon name="i-heroicons-arrow-right" class="ml-2" />
          </UButton>
        </div>
      </UContainer>
    </section>
  </div>
</template>
