<script setup lang="ts">
const navigation = [
  {
    label: 'Agentur',
    to: '/agentur',
    children: [
      { label: 'Über uns', to: '/agentur' },
      { label: 'Team', to: '/agentur#team' }
    ]
  },
  {
    label: 'Service',
    to: '/services',
    children: [
      { label: 'Filmproduktion', to: '/services/filmproduktion' },
      { label: 'Webdesign', to: '/services/webdesign' },
      { label: 'Software Entwicklung', to: '/services/software' },
      { label: 'Social Media Marketing', to: '/services/marketing' }
    ]
  },
  { label: 'Studio', to: '/studio' },
  { label: 'Success Stories', to: '/projekte' },
  { label: 'Kontakt', to: '/kontakt' }
]

const isScrolled = ref(false)
const mobileMenuOpen = ref(false)
const activeDropdown = ref<string | null>(null)

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})

function handleScroll() {
  isScrolled.value = window.scrollY > 50
}

function toggleDropdown(label: string) {
  activeDropdown.value = activeDropdown.value === label ? null : label
}

function closeDropdown() {
  activeDropdown.value = null
}
</script>

<template>
  <div class="min-h-screen bg-gray-950">
    <!-- Navigation -->
    <header
      class="fixed top-0 left-0 right-0 z-50 transition-all duration-300"
      :class="isScrolled ? 'bg-gray-950/95 backdrop-blur-md shadow-lg' : 'bg-transparent'"
    >
      <UContainer>
        <nav class="flex items-center justify-between h-20">
          <!-- Logo -->
          <NuxtLink to="/" class="flex items-center gap-2 group">
            <span class="text-2xl font-black text-white tracking-tight">
              <span class="text-orange-500">peppermint</span>
              <span class="block text-sm font-bold tracking-widest">digital</span>
            </span>
          </NuxtLink>

          <!-- Desktop Navigation -->
          <div class="hidden lg:flex items-center gap-6">
            <div
              v-for="item in navigation"
              :key="item.label"
              class="relative"
              @mouseenter="item.children ? toggleDropdown(item.label) : null"
              @mouseleave="item.children ? closeDropdown() : null"
            >
              <NuxtLink
                v-if="!item.children"
                :to="item.to"
                class="text-gray-300 hover:text-orange-500 transition-colors duration-300 font-medium py-2"
              >
                {{ item.label }}
              </NuxtLink>

              <button
                v-else
                class="flex items-center gap-1 text-gray-300 hover:text-orange-500 transition-colors duration-300 font-medium py-2"
                @click="toggleDropdown(item.label)"
              >
                {{ item.label }}
                <UIcon
                  name="i-heroicons-chevron-down"
                  class="w-4 h-4 transition-transform duration-200"
                  :class="activeDropdown === item.label ? 'rotate-180' : ''"
                />
              </button>

              <!-- Dropdown Menu -->
              <div
                v-if="item.children && activeDropdown === item.label"
                class="absolute top-full left-0 mt-2 w-56 bg-gray-900 border border-gray-800 rounded-xl shadow-xl overflow-hidden"
              >
                <NuxtLink
                  v-for="child in item.children"
                  :key="child.label"
                  :to="child.to"
                  class="block px-4 py-3 text-gray-300 hover:text-orange-500 hover:bg-gray-800 transition-all duration-200"
                  @click="closeDropdown"
                >
                  {{ child.label }}
                </NuxtLink>
              </div>
            </div>

            <UButton
              color="primary"
              variant="solid"
              class="bg-orange-500 hover:bg-orange-600 ml-4"
              to="/kontakt"
            >
              Projekt starten
            </UButton>
          </div>

          <!-- Mobile Menu Button -->
          <UButton
            variant="ghost"
            color="white"
            class="lg:hidden"
            :icon="mobileMenuOpen ? 'i-heroicons-x-mark' : 'i-heroicons-bars-3'"
            aria-label="Menu"
            @click="mobileMenuOpen = !mobileMenuOpen"
          />
        </nav>

        <!-- Mobile Menu -->
        <div
          v-if="mobileMenuOpen"
          class="lg:hidden absolute top-20 left-0 right-0 bg-gray-950/98 backdrop-blur-lg border-t border-gray-800"
        >
          <div class="px-4 py-6 space-y-4">
            <template v-for="item in navigation" :key="item.label">
              <div v-if="item.children">
                <button
                  class="flex items-center justify-between w-full py-2 text-gray-300 font-medium"
                  @click="toggleDropdown(item.label)"
                >
                  {{ item.label }}
                  <UIcon
                    name="i-heroicons-chevron-down"
                    class="w-4 h-4 transition-transform duration-200"
                    :class="activeDropdown === item.label ? 'rotate-180' : ''"
                  />
                </button>
                <div v-if="activeDropdown === item.label" class="pl-4 mt-2 space-y-2">
                  <NuxtLink
                    v-for="child in item.children"
                    :key="child.label"
                    :to="child.to"
                    class="block py-2 text-gray-400 hover:text-orange-500 transition-colors"
                    @click="mobileMenuOpen = false"
                  >
                    {{ child.label }}
                  </NuxtLink>
                </div>
              </div>
              <NuxtLink
                v-else
                :to="item.to"
                class="block py-2 text-gray-300 hover:text-orange-500 transition-colors font-medium"
                @click="mobileMenuOpen = false"
              >
                {{ item.label }}
              </NuxtLink>
            </template>
            <UButton
              color="primary"
              variant="solid"
              class="w-full bg-orange-500 hover:bg-orange-600 mt-4"
              to="/kontakt"
              @click="mobileMenuOpen = false"
            >
              Projekt starten
            </UButton>
          </div>
        </div>
      </UContainer>
    </header>

    <!-- Main Content -->
    <main>
      <slot />
    </main>

    <!-- Footer -->
    <footer class="bg-gray-900 border-t border-gray-800">
      <UContainer class="py-12">
        <div class="grid grid-cols-1 md:grid-cols-4 gap-8">
          <!-- Logo & Description -->
          <div class="md:col-span-2">
            <NuxtLink to="/" class="inline-block">
              <span class="text-2xl font-black text-white tracking-tight">
                <span class="text-orange-500">peppermint</span>
                <span class="block text-sm font-bold tracking-widest">digital</span>
              </span>
            </NuxtLink>
            <p class="mt-4 text-gray-400 max-w-md">
              Ihre Kreativ- und Digitalagentur aus Hannover. Filmproduktion, Webentwicklung und maßgeschneiderte Softwarelösungen.
            </p>
          </div>

          <!-- Services Links -->
          <div>
            <h4 class="text-white font-semibold mb-4">Services</h4>
            <ul class="space-y-2">
              <li><NuxtLink to="/services/filmproduktion" class="text-gray-400 hover:text-orange-500 transition-colors">Filmproduktion</NuxtLink></li>
              <li><NuxtLink to="/services/webdesign" class="text-gray-400 hover:text-orange-500 transition-colors">Webdesign</NuxtLink></li>
              <li><NuxtLink to="/services/software" class="text-gray-400 hover:text-orange-500 transition-colors">Software</NuxtLink></li>
              <li><NuxtLink to="/services/marketing" class="text-gray-400 hover:text-orange-500 transition-colors">Marketing</NuxtLink></li>
            </ul>
          </div>

          <!-- Contact -->
          <div>
            <h4 class="text-white font-semibold mb-4">Kontakt</h4>
            <ul class="space-y-2 text-gray-400">
              <li>Hannover / Langenhagen</li>
              <li>
                <a href="tel:+4917631890002" class="hover:text-orange-500 transition-colors">
                  +49 (0) 176 3189 0002
                </a>
              </li>
            </ul>
            <!-- Social Links -->
            <div class="flex gap-4 mt-4">
              <a href="#" class="text-gray-400 hover:text-orange-500 transition-colors" aria-label="Instagram">
                <UIcon name="i-simple-icons-instagram" class="w-5 h-5" />
              </a>
              <a href="#" class="text-gray-400 hover:text-orange-500 transition-colors" aria-label="TikTok">
                <UIcon name="i-simple-icons-tiktok" class="w-5 h-5" />
              </a>
              <a href="#" class="text-gray-400 hover:text-orange-500 transition-colors" aria-label="LinkedIn">
                <UIcon name="i-simple-icons-linkedin" class="w-5 h-5" />
              </a>
            </div>
          </div>
        </div>

        <!-- Bottom Bar -->
        <div class="mt-12 pt-8 border-t border-gray-800 flex flex-col md:flex-row justify-between items-center gap-4">
          <p class="text-gray-500 text-sm">
            © {{ new Date().getFullYear() }} Peppermint Digital. Alle Rechte vorbehalten.
          </p>
          <div class="flex gap-6 text-sm">
            <NuxtLink to="/impressum" class="text-gray-500 hover:text-orange-500 transition-colors">Impressum</NuxtLink>
            <NuxtLink to="/datenschutz" class="text-gray-500 hover:text-orange-500 transition-colors">Datenschutz</NuxtLink>
            <NuxtLink to="/kontakt" class="text-gray-500 hover:text-orange-500 transition-colors">Kontakt</NuxtLink>
          </div>
        </div>
      </UContainer>
    </footer>
  </div>
</template>
