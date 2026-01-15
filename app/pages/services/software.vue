<script setup lang="ts">
const leistungen = [
  { title: 'Web Applikationen', description: 'Maßgeschneiderte Browser-basierte Anwendungen' },
  { title: 'Mobile Apps', description: 'Native und Cross-Platform Apps für iOS und Android' },
  { title: 'API Entwicklung', description: 'Robuste Schnittstellen für Ihre Systeme' },
  { title: 'Datenbanken', description: 'Effiziente Datenhaltung und -verarbeitung' },
  { title: 'Cloud Solutions', description: 'Skalierbare Cloud-Infrastruktur' },
  { title: 'Automatisierung', description: 'Prozessoptimierung durch intelligente Systeme' },
]
</script>

<template>
  <div>
    <!-- Hero -->
    <section class="pt-32 pb-20 bg-gray-950">
      <UContainer>
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-16 items-center">
          <div>
            <UBadge color="orange" variant="soft" class="mb-6">Individuelle Lösungen</UBadge>
            <h1 class="text-5xl md:text-6xl font-black text-white mb-6">
              Software<br />
              <span class="text-orange-500">Entwicklung</span>
            </h1>
            <p class="text-xl text-gray-400 leading-relaxed mb-8">
              Digitalisierung von Prozessen, Automatisierung von Abläufen oder Vereinheitlichung von unterschiedlichen Services. Wir entwickeln professionelle App- und Software-Lösungen für Sie, Ihre Kunden und Partner.
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
            <UIcon name="i-heroicons-code-bracket" class="w-24 h-24 text-orange-500" />
          </div>
        </div>
      </UContainer>
    </section>

    <!-- Leistungen -->
    <section class="py-24 bg-gray-900">
      <UContainer>
        <div class="text-center mb-16">
          <UBadge color="orange" variant="soft" class="mb-4">Unsere Leistungen</UBadge>
          <h2 class="text-4xl font-black text-white">Was wir entwickeln</h2>
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

    <!-- CTA -->
    <section class="py-24 bg-gray-950">
      <UContainer>
        <div class="text-center max-w-3xl mx-auto">
          <h2 class="text-4xl font-black text-white mb-6">
            Ihre individuelle Softwarelösung
          </h2>
          <p class="text-gray-400 text-lg mb-10">
            Von der ersten Idee bis zum fertigen Produkt – wir begleiten Sie durch den gesamten Entwicklungsprozess.
          </p>
          <UButton
            size="xl"
            color="primary"
            class="bg-orange-500 hover:bg-orange-600"
            to="/kontakt"
          >
            Beratungsgespräch vereinbaren
            <UIcon name="i-heroicons-arrow-right" class="ml-2" />
          </UButton>
        </div>
      </UContainer>
    </section>
  </div>
</template>
