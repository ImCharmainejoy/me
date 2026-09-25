<template>
  <v-container fluid class="skills-wrapper py-10 px-4 px-md-8" id="skills">
    <div class="max-width-container mx-auto">

      <!-- Section Header -->
      <div class="text-center mb-8">
        <h1 class="text-h3 font-weight-bold gold-gradient-text tracking-wide mb-2">
          TECHNICAL SKILLS
        </h1>
        <p class="text-subtitle-1 text-medium-emphasis">
          Technologies, frameworks, and tools I use to build modern web applications.
        </p>
      </div>

      <!-- Category Filter Tabs -->
      <div class="d-flex justify-center mb-8">
        <v-tabs v-model="activeTab" color="#B88E30" align-tabs="center" density="comfortable" class="custom-tabs">
          <v-tab value="all" class="text-caption text-md-button font-weight-bold">All Skills</v-tab>
          <v-tab value="frontend" class="text-caption text-md-button font-weight-bold">Frontend</v-tab>
          <v-tab value="backend" class="text-caption text-md-button font-weight-bold">Backend & API</v-tab>
          <v-tab value="tools" class="text-caption text-md-button font-weight-bold">Tools & Build</v-tab>
        </v-tabs>
      </div>

      <!-- Skills Cards Grid -->
      <v-row>
        <v-col v-for="(skill, index) in filteredSkills" :key="index" cols="12" sm="6" md="4" class="d-flex">
          <v-card class="chic-card flex-grow-1 pa-6 d-flex flex-column" elevation="1" rounded="xl">
            <!-- Card Header: Icon, Name & Level -->
            <div class="d-flex align-center justify-space-between mb-3">
              <div class="d-flex align-center ga-3">
                <v-avatar color="#F8F4EB" size="44" class="skill-avatar">
                  <v-icon size="22" color="#B88E30">{{ skill.icon }}</v-icon>
                </v-avatar>
                <div>
                  <h3 class="text-subtitle-1 font-weight-bold text-high-emphasis leading-tight">
                    {{ skill.name }}
                  </h3>
                  <span class="text-caption text-medium-emphasis">{{ skill.categoryLabel }}</span>
                </div>
              </div>

              <!-- Tag for Experience/Proficiency -->
              <v-chip size="x-small" variant="flat" class="chic-level-chip font-weight-bold text-uppercase">
                {{ skill.level }}
              </v-chip>
            </div>

            <!-- Description & Stacks -->
            <v-card-text class="pa-0 pt-2 flex-grow-1 text-body-2 text-medium-emphasis">
              {{ skill.description }}
            </v-card-text>

            <!-- Bottom Progress Line -->
            <div class="mt-4 pt-2">
              <div class="d-flex justify-space-between text-caption text-medium-emphasis mb-1">
                <span>Proficiency</span>
                <span class="font-weight-bold gold-text">{{ skill.proficiency }}%</span>
              </div>
              <v-progress-linear :model-value="skill.proficiency" color="#C5A059" bg-color="#F3EFE6" height="6"
                rounded></v-progress-linear>
            </div>

            <!-- Subtle Paw Accent -->
            <div class="chic-bottom-paw">
              <v-icon size="12" color="#E6D3A3">mdi-paw</v-icon>
            </div>
          </v-card>
        </v-col>
      </v-row>

    </div>
  </v-container>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue'

const activeTab = ref('all')

// Pure Skill Items
const skills = ref([
  // Frontend Skills
  {
    name: 'Vue.js',
    category: 'frontend',
    categoryLabel: 'Frontend Framework',
    level: 'Advanced',
    proficiency: 92,
    icon: 'mdi-vuejs',
    description: 'Extensive production experience in Vue 2 and modern Vue 3 (Composition API & Script Setup).'
  },
  {
    name: 'Nuxt.js',
    category: 'frontend',
    categoryLabel: 'Vue Framework',
    level: 'Advanced',
    proficiency: 88,
    icon: 'mdi-nuxt',
    description: 'Building SEO-friendly SSR and SSG applications with Nuxt 2 & Nuxt 3.'
  },
  {
    name: 'JavaScript / ES6+',
    category: 'frontend',
    categoryLabel: 'Language',
    level: 'Advanced',
    proficiency: 90,
    icon: 'mdi-language-javascript',
    description: 'Deep understanding of modern DOM manipulation, async patterns, closures, and promises.'
  },
  {
    name: 'TypeScript',
    category: 'frontend',
    categoryLabel: 'Language',
    level: 'Intermediate',
    proficiency: 78,
    icon: 'mdi-language-typescript',
    description: 'Type-safe frontend development, interface modeling, and strict component prop typing.'
  },
  {
    name: 'Vuetify & CSS Frameworks',
    category: 'frontend',
    categoryLabel: 'UI Component Library',
    level: 'Advanced',
    proficiency: 94,
    icon: 'mdi-vuetify',
    description: 'Proficient with Vuetify 2 & 3, Tailwind CSS, Flexbox, CSS Grid, and responsive layout systems.'
  },
  {
    name: 'State Management (Pinia/Vuex)',
    category: 'frontend',
    categoryLabel: 'Architecture',
    level: 'Advanced',
    proficiency: 85,
    icon: 'mdi-database-sync',
    description: 'Centralized state handling using Vuex v3/v4 and modern Pinia stores.'
  },

  // Backend & APIs
  {
    name: 'RESTful APIs & Axios',
    category: 'backend',
    categoryLabel: 'Integration',
    level: 'Advanced',
    proficiency: 88,
    icon: 'mdi-api',
    description: 'Integrating asynchronous REST endpoints, handling JWT authentication, request interceptors, and error boundaries.'
  },
  {
    name: 'Inertia.js',
    category: 'backend',
    categoryLabel: 'Fullstack Adapter',
    level: 'Intermediate',
    proficiency: 75,
    icon: 'mdi-swap-horizontal-bold',
    description: 'Building monolithic modern web apps connecting Vue 3 frontend components to backend routes seamlessly.'
  },

  // Tools & Ecosystem
  {
    name: 'Vite & Webpack',
    category: 'tools',
    categoryLabel: 'Build Tools',
    level: 'Intermediate',
    proficiency: 80,
    icon: 'mdi-lightning-bolt',
    description: 'Configuring modern frontend build tools, environment variables, and module bundling.'
  },
  {
    name: 'Git & Version Control',
    category: 'tools',
    categoryLabel: 'Workflow',
    level: 'Advanced',
    proficiency: 88,
    icon: 'mdi-git',
    description: 'Branching strategies, pull requests, code reviews, and version management in collaborative environments.'
  }
])

// Filter Logic for Tab Navigation
const filteredSkills = computed(() => {
  if (activeTab.value === 'all') return skills.value
  return skills.value.filter(s => s.category === activeTab.value)
})
</script>

<style scoped>
/* Container Setup */
.skills-wrapper {
  background-color: #FAFAFA;
  min-height: 100vh;
}

.max-width-container {
  max-width: 1140px;
}

/* Typography & Colors */
.gold-gradient-text {
  background: linear-gradient(135deg, #8A6D2B 0%, #C5A059 50%, #8A6D2B 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  letter-spacing: 2px !important;
}

.gold-text {
  color: #B88E30;
}

.leading-tight {
  line-height: 1.25;
}

/* Custom Tabs */
.custom-tabs :deep(.v-slide-group-item--active) {
  color: #B88E30 !important;
}

/* Chic Skill Cards */
.chic-card {
  background-color: #FFFFFF !important;
  border: 1px solid #EAE5D9 !important;
  box-shadow: 0 8px 24px rgba(184, 142, 48, 0.05) !important;
  position: relative;
  overflow: hidden;
  transition: transform 0.3s cubic-bezier(0.25, 0.8, 0.25, 1), box-shadow 0.3s ease;
}

.chic-card:hover {
  transform: translateY(-50px);
  transform: translateY(-6px);
  box-shadow: 0 14px 32px rgba(184, 142, 48, 0.12) !important;
  border-color: #D4AF37 !important;
}

.skill-avatar {
  border: 1px solid #EAE5D9;
}

.chic-level-chip {
  background-color: #F8F4EB !important;
  color: #8A6D2B !important;
  border: 1px solid #EAE5D9;
  letter-spacing: 0.5px;
}

/* Subtle Paw Accent */
.chic-bottom-paw {
  position: absolute;
  bottom: 8px;
  right: 10px;
  opacity: 0.5;
}
</style>