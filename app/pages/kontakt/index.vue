<script setup lang="ts">
const form = reactive({
  vorname: '',
  nachname: '',
  telefon: '',
  email: '',
  betreff: '',
  nachricht: ''
})

const kontaktdaten = {
  telefon: '+49 (0) 176 3189 0002',
  email: 'info@peppermint-digital.de',
  adresse: 'Hannover / Langenhagen'
}

const socialLinks = [
  { name: 'Instagram', icon: 'i-simple-icons-instagram', url: '#' },
  { name: 'TikTok', icon: 'i-simple-icons-tiktok', url: '#' },
  { name: 'LinkedIn', icon: 'i-simple-icons-linkedin', url: '#' }
]

const handleSubmit = () => {
  // Form submission logic
  console.log('Form submitted:', form)
}
</script>

<template>
  <div>
    <!-- Hero -->
    <section class="pt-32 pb-20 bg-gray-950 relative overflow-hidden">
      <div class="absolute inset-0 bg-gradient-to-br from-orange-500/10 to-transparent" />
      <UContainer class="relative">
        <div class="text-center max-w-4xl mx-auto">
          <UBadge color="orange" variant="soft" class="mb-6">Wir freuen uns auf Sie</UBadge>
          <h1 class="text-5xl md:text-7xl font-black text-white mb-6">
            Kontakt
          </h1>
          <p class="text-xl text-gray-400 leading-relaxed max-w-2xl mx-auto">
            Sie haben Fragen? Wir haben Antworten! Kontaktieren Sie uns gerne per Nachricht oder zögern Sie nicht, uns anzurufen.
          </p>
        </div>
      </UContainer>
    </section>

    <!-- Contact Section -->
    <section class="py-24 bg-gray-900">
      <UContainer>
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-16">
          <!-- Left side - Info -->
          <div>
            <UBadge color="orange" variant="soft" class="mb-4">Sprechen Sie uns an</UBadge>
            <h2 class="text-4xl font-black text-white mb-6">Lassen Sie uns reden</h2>
            <p class="text-gray-400 text-lg mb-8">
              Gerne vereinbaren wir einen direkten Termin mit Ihnen. Erzählen Sie uns von Ihrem Projekt und wir finden gemeinsam die beste Lösung.
            </p>

            <!-- Contact Info -->
            <div class="space-y-6 mb-10">
              <div class="flex items-center gap-4">
                <div class="w-12 h-12 bg-orange-500/10 rounded-xl flex items-center justify-center">
                  <UIcon name="i-heroicons-phone" class="w-6 h-6 text-orange-500" />
                </div>
                <div>
                  <p class="text-gray-500 text-sm">Telefon</p>
                  <a :href="`tel:${kontaktdaten.telefon.replace(/\s/g, '')}`" class="text-white font-semibold hover:text-orange-500 transition-colors">
                    {{ kontaktdaten.telefon }}
                  </a>
                </div>
              </div>

              <div class="flex items-center gap-4">
                <div class="w-12 h-12 bg-orange-500/10 rounded-xl flex items-center justify-center">
                  <UIcon name="i-heroicons-envelope" class="w-6 h-6 text-orange-500" />
                </div>
                <div>
                  <p class="text-gray-500 text-sm">E-Mail</p>
                  <a :href="`mailto:${kontaktdaten.email}`" class="text-white font-semibold hover:text-orange-500 transition-colors">
                    {{ kontaktdaten.email }}
                  </a>
                </div>
              </div>

              <div class="flex items-center gap-4">
                <div class="w-12 h-12 bg-orange-500/10 rounded-xl flex items-center justify-center">
                  <UIcon name="i-heroicons-map-pin" class="w-6 h-6 text-orange-500" />
                </div>
                <div>
                  <p class="text-gray-500 text-sm">Standort</p>
                  <p class="text-white font-semibold">{{ kontaktdaten.adresse }}</p>
                </div>
              </div>
            </div>

            <!-- Social Links -->
            <div>
              <p class="text-gray-500 mb-4">Folgen Sie uns</p>
              <div class="flex gap-4">
                <a
                  v-for="social in socialLinks"
                  :key="social.name"
                  :href="social.url"
                  class="w-12 h-12 bg-gray-800 rounded-xl flex items-center justify-center hover:bg-orange-500 transition-all duration-300 group"
                  :aria-label="social.name"
                >
                  <UIcon :name="social.icon" class="w-5 h-5 text-gray-400 group-hover:text-white transition-colors" />
                </a>
              </div>
            </div>
          </div>

          <!-- Right side - Form -->
          <div class="bg-gray-800 rounded-3xl p-8 md:p-10">
            <h3 class="text-2xl font-bold text-white mb-6">Nachricht senden</h3>

            <form @submit.prevent="handleSubmit" class="space-y-6">
              <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                <div>
                  <label for="vorname" class="block text-gray-400 text-sm mb-2">Vorname</label>
                  <input
                    id="vorname"
                    v-model="form.vorname"
                    type="text"
                    class="w-full bg-gray-900 border border-gray-700 rounded-xl px-4 py-3 text-white placeholder-gray-500 focus:outline-none focus:border-orange-500 transition-colors"
                    placeholder="Ihr Vorname"
                  />
                </div>
                <div>
                  <label for="nachname" class="block text-gray-400 text-sm mb-2">Nachname</label>
                  <input
                    id="nachname"
                    v-model="form.nachname"
                    type="text"
                    class="w-full bg-gray-900 border border-gray-700 rounded-xl px-4 py-3 text-white placeholder-gray-500 focus:outline-none focus:border-orange-500 transition-colors"
                    placeholder="Ihr Nachname"
                  />
                </div>
              </div>

              <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                <div>
                  <label for="telefon" class="block text-gray-400 text-sm mb-2">Telefon</label>
                  <input
                    id="telefon"
                    v-model="form.telefon"
                    type="tel"
                    class="w-full bg-gray-900 border border-gray-700 rounded-xl px-4 py-3 text-white placeholder-gray-500 focus:outline-none focus:border-orange-500 transition-colors"
                    placeholder="Ihre Telefonnummer"
                  />
                </div>
                <div>
                  <label for="email" class="block text-gray-400 text-sm mb-2">E-Mail</label>
                  <input
                    id="email"
                    v-model="form.email"
                    type="email"
                    class="w-full bg-gray-900 border border-gray-700 rounded-xl px-4 py-3 text-white placeholder-gray-500 focus:outline-none focus:border-orange-500 transition-colors"
                    placeholder="Ihre E-Mail-Adresse"
                  />
                </div>
              </div>

              <div>
                <label for="betreff" class="block text-gray-400 text-sm mb-2">Wie können wir Ihnen weiterhelfen?</label>
                <input
                  id="betreff"
                  v-model="form.betreff"
                  type="text"
                  class="w-full bg-gray-900 border border-gray-700 rounded-xl px-4 py-3 text-white placeholder-gray-500 focus:outline-none focus:border-orange-500 transition-colors"
                  placeholder="Ihr Anliegen"
                />
              </div>

              <div>
                <label for="nachricht" class="block text-gray-400 text-sm mb-2">Nachricht</label>
                <textarea
                  id="nachricht"
                  v-model="form.nachricht"
                  rows="5"
                  class="w-full bg-gray-900 border border-gray-700 rounded-xl px-4 py-3 text-white placeholder-gray-500 focus:outline-none focus:border-orange-500 transition-colors resize-none"
                  placeholder="Nachricht schreiben"
                />
              </div>

              <UButton
                type="submit"
                size="xl"
                color="primary"
                class="w-full bg-orange-500 hover:bg-orange-600"
              >
                Senden
                <UIcon name="i-heroicons-paper-airplane" class="ml-2" />
              </UButton>
            </form>
          </div>
        </div>
      </UContainer>
    </section>

    <!-- Map / Location -->
    <section class="py-24 bg-gray-950">
      <UContainer>
        <div class="text-center max-w-3xl mx-auto mb-16">
          <UBadge color="orange" variant="soft" class="mb-4">Unser Standort</UBadge>
          <h2 class="text-4xl font-black text-white mb-6">Besuchen Sie uns</h2>
          <p class="text-gray-400 text-lg">
            Unser Studio befindet sich in Hannover/Langenhagen – zentral gelegen und optimal erreichbar.
          </p>
        </div>

        <div class="aspect-[21/9] bg-gray-900 rounded-3xl flex items-center justify-center">
          <div class="text-center">
            <UIcon name="i-heroicons-map" class="w-16 h-16 text-orange-500 mb-4" />
            <p class="text-gray-400">Hannover / Langenhagen</p>
          </div>
        </div>
      </UContainer>
    </section>
  </div>
</template>
