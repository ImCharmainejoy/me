<template>
  <v-container fluid class="hobbies-wrapper pt-4 pb-10 px-4 px-md-8" id="hobbies">
    <div class="max-width-container mx-auto">

      <!-- Section Header -->
      <div class="text-center mb-10">
        <h1 class="text-h3 font-weight-bold gold-gradient-text tracking-wide mb-2">
          HOBBIES & INTERESTS
        </h1>
        <p class="text-subtitle-1 text-medium-emphasis">
          Activities, strategy games, and personal interests I enjoy during my free time.
        </p>
      </div>

      <!-- Hobbies Cards Grid -->
      <v-row justify="center">
        <v-col v-for="(item, i) in items" :key="i" cols="12" sm="6" md="4" class="d-flex">
          <v-card class="chic-hobby-card flex-grow-1 pa-5 d-flex flex-column" elevation="1" rounded="xl">
            <!-- Image with Hover Overlay -->
            <v-hover v-slot="{ isHovering, props }">
              <v-img v-bind="props" :src="item.img" height="220" cover
                class="rounded-lg position-relative overflow-hidden mb-4 hobby-img-border">
                <!-- Hover Overlay -->
                <div :class="isHovering ? 'opacity-100' : 'opacity-0'"
                  class="overlay-panel d-flex align-center justify-center transition-opacity">
                  <v-btn variant="flat" color="#B88E30" class="text-white font-weight-bold text-caption" rounded="lg"
                    size="small" :href="item.img" target="_blank" prepend-icon="mdi-eye-outline">
                    View Photo
                  </v-btn>
                </div>
              </v-img>
            </v-hover>

            <!-- Top Badge / Header -->
            <div class="d-flex align-center justify-space-between mb-2">
              <span class="text-caption font-weight-bold gold-accent-text tracking-wide">
                INTEREST 0{{ i + 1 }}
              </span>
              <v-icon size="18" color="#D4AF37">{{ item.icon }}</v-icon>
            </div>

            <!-- Hobby Title -->
            <h3 class="text-subtitle-1 font-weight-bold text-high-emphasis mb-2 leading-tight">
              {{ item.title }}
            </h3>

            <!-- Hobby Description -->
            <p class="text-body-2 text-medium-emphasis flex-grow-1 mb-0 leading-relaxed">
              {{ item.text }}
            </p>

            <!-- Subtle Decorative Paw Accent -->
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
import { ref } from 'vue'

import hobby1 from '@/assets/images/hob1.png'
import hobby2 from '@/assets/images/hob2.png'
import hobby3 from '@/assets/images/hob3.png'

const items = ref([
  {
    title: 'Game of the Generals',
    text: 'Playing Game of the Generals (Salpakan), testing psychological strategy, memory, and tactical deception.',
    icon: 'mdi-shield-outline',
    img: hobby1
  },
  {
    title: 'Chess',
    text: 'Engaging in classic chess matches to hone strategic foresight, analytical skills, and tactical decision-making.',
    icon: 'mdi-chess-king',
    img: hobby2
  },
  {
    title: 'Cup / Tower Stacking',
    text: 'Practicing speed stacking and dexterity games that demand high hand-eye coordination, precision, and focus.',
    icon: 'mdi-layers-triple-outline',
    img: hobby3
  }
])
</script>

<style scoped>
/* Container Setup */
.hobbies-wrapper {
  background-color: #FAFAFA;
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

.leading-relaxed {
  line-height: 1.6;
}

/* Chic Hobby Cards */
.chic-hobby-card {
  background-color: #FFFFFF !important;
  border: 1px solid #EAE5D9 !important;
  box-shadow: 0 10px 30px rgba(184, 142, 48, 0.05) !important;
  position: relative;
  overflow: hidden;
  transition: transform 0.3s cubic-bezier(0.25, 0.8, 0.25, 1), box-shadow 0.3s ease;
}

.chic-hobby-card:hover {
  transform: translateY(-6px);
  box-shadow: 0 16px 36px rgba(184, 142, 48, 0.12) !important;
  border-color: #D4AF37 !important;
}

.hobby-img-border {
  border: 1px solid #EAE5D9;
}

/* Image Hover Overlay */
.overlay-panel {
  height: 100%;
  background: rgba(20, 20, 20, 0.45);
  backdrop-filter: blur(2px);
}

.transition-opacity {
  transition: opacity 0.3s ease-in-out;
}

/* Subtle Paw Accent */
.chic-bottom-paw {
  position: absolute;
  bottom: 8px;
  right: 12px;
  opacity: 0.5;
}
</style>