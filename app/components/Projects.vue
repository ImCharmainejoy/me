<template>
  <v-container fluid class="projects-wrapper py-10 px-4 px-md-8" id="projects">
    <div class="max-width-container mx-auto">

      <!-- Section Header -->
      <div class="text-center mb-10">
        <h1 class="text-h3 font-weight-bold gold-gradient-text tracking-wide mb-2">
          FEATURED PROJECTS
        </h1>
        <p class="text-subtitle-1 text-medium-emphasis">
          A showcase of key web applications and systems I've built and engineered.
        </p>
      </div>

      <!-- Alternating Project Showcase Grid -->
      <div class="d-flex flex-column ga-10">
        <v-card v-for="(item, i) in items" :key="i" class="chic-project-card pa-6 pa-md-8" elevation="1" rounded="xl">
          <v-row align="center" justify="center">

            <!-- Project Image Column (Alternates side on desktop) -->
            <v-col cols="12" md="6" :order-md="i % 2 === 0 ? 1 : 2">
              <v-hover v-slot="{ isHovering, props }">
                <v-img v-bind="props" :src="item.img" height="280" cover
                  class="project-image-container rounded-lg position-relative">
                  <!-- Hover Overlay -->
                  <div :class="isHovering ? 'opacity-100' : 'opacity-0'"
                    class="overlay-panel d-flex align-center justify-center ga-3 transition-opacity">
                    <v-btn variant="flat" color="#B88E30"
                      class="text-white font-weight-bold text-caption text-md-button px-5" rounded="lg"
                      :href="item.link" target="_blank" prepend-icon="mdi-github">
                      View Source
                    </v-btn>
                  </div>
                </v-img>
              </v-hover>
            </v-col>

            <!-- Project Details Column -->
            <v-col cols="12" md="6" :order-md="i % 2 === 0 ? 2 : 1" class="d-flex flex-column justify-center">
              <div class="px-md-4">
                <!-- Project Index & Tech Tag -->
                <div class="d-flex align-center justify-space-between mb-2">
                  <span class="text-caption font-weight-bold gold-accent-text tracking-wide">
                    PROJECT 0{{ i + 1 }}
                  </span>
                  <v-icon size="20" color="#D4AF37">mdi-folder-star-outline</v-icon>
                </div>

                <!-- Title -->
                <h2 class="text-h5 font-weight-bold text-high-emphasis mb-3 leading-tight">
                  {{ item.title }}
                </h2>

                <!-- Stack Description -->
                <p class="text-body-2 text-medium-emphasis mb-4 bio-text-content">
                  {{ item.text }}
                </p>

                <!-- Stack Chips Parsing -->
                <div class="d-flex flex-wrap ga-2 mb-4">
                  <v-chip v-for="(tech, index) in item.tags" :key="index" size="small" variant="outlined"
                    class="chic-chip">
                    {{ tech }}
                  </v-chip>
                </div>

                <!-- GitHub Link Button -->
                <div>
                  <v-btn variant="text" color="#B88E30" class="pa-0 font-weight-bold text-caption text-md-button"
                    :href="item.link" target="_blank" append-icon="mdi-arrow-right">
                    Explore Project
                  </v-btn>
                </div>
              </div>
            </v-col>

          </v-row>

          <!-- Subtle Decorative Paw Accent -->
          <div class="chic-bottom-paw">
            <v-icon size="14" color="#E6D3A3">mdi-paw</v-icon>
          </div>
        </v-card>
      </div>

    </div>
  </v-container>
</template>

<script setup lang="ts">
import { ref } from 'vue'

import project1 from '@/assets/images/proj1.png'
import project2 from '@/assets/images/proj2.png'
import project3 from '@/assets/images/proj3.png'

const items = ref([
  {
    title: 'School Class & Records Management System',
    text: 'A robust web application designed for managing class rosters and academic records efficiently.',
    tags: ['Vue 2', 'JavaScript', 'Vuetify 2', 'Vuex 3'],
    link: 'https://github.com/ImCharmainejoy/Iamcj.',
    img: project1
  },
  {
    title: 'Sales Tracker System',
    text: 'A modern, high-performance sales monitoring dashboard built with a modern full-stack tech pipeline.',
    tags: ['Vue 3', 'TypeScript', 'Tailwind CSS v3', 'Vite v7', 'Inertia.js v2'],
    link: 'https://github.com/ImCharmainejoy/salesTracker',
    img: project2
  },
  {
    title: 'Vaccination System',
    text: 'An end-to-end vaccination logging and management portal built with server-side rendering support.',
    tags: ['Vue 2', 'Nuxt 2', 'JavaScript', 'Vuetify 2', 'Vuex 3'],
    link: 'https://github.com/ImCharmainejoy/Iamcj.',
    img: project3
  }
])
</script>

<style scoped>
/* Container Setup */
.projects-wrapper {
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

.gold-accent-text {
  color: #B88E30;
}

.leading-tight {
  line-height: 1.3;
}

/* Chic Project Card Styling */
.chic-project-card {
  background-color: #FFFFFF !important;
  border: 1px solid #EAE5D9 !important;
  box-shadow: 0 10px 30px rgba(184, 142, 48, 0.05) !important;
  position: relative;
  overflow: hidden;
  transition: transform 0.3s cubic-bezier(0.25, 0.8, 0.25, 1), box-shadow 0.3s ease;
}

.chic-project-card:hover {
  transform: translateY(-6px);
  box-shadow: 0 16px 36px rgba(184, 142, 48, 0.12) !important;
  border-color: #D4AF37 !important;
}

/* Image & Overlay */
.project-image-container {
  border: 1px solid #EAE5D9;
}

.overlay-panel {
  height: 100%;
  background: rgba(20, 20, 20, 0.45);
  backdrop-filter: blur(2px);
}

.transition-opacity {
  transition: opacity 0.3s ease-in-out;
}

/* Tags & Chips */
.chic-chip {
  border-color: #EAE5D9 !important;
  color: #555555 !important;
  background-color: #F8F4EB !important;
  font-weight: 500;
}

.bio-text-content {
  line-height: 1.6;
}

/* Subtle Paw Accent */
.chic-bottom-paw {
  position: absolute;
  bottom: 10px;
  right: 14px;
  opacity: 0.5;
}
</style>