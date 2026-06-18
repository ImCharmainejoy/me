<template>
  <v-container id="hobbies" class="pa-0">
    <v-card flat color="blue" class="mb-5">
      <v-card-title class="font-style text-h5 text-center">Hobbies & Interests</v-card-title>
    </v-card>
    <v-card id="hobbies" variant="flat"
      subtitle="These are some of my hobbies and interests that I enjoy during my free time.">
      <v-row align="center" class="fill-height" justify="center">
        <template v-for="(item, i) in items" :key="i">
          <v-col cols="4" md="4">
            <v-img :src="item.img" :width="smAndUp ? '200' : '150'" cover class="rounded-lg" hover>
              <div :class="isHovering ? 'opacity-100' : 'opacity-0'"
                class="d-flex align-center justify-center transition-opacity duration-500"
                style="height: 100%; background: rgba(0,0,0,0.4); color: white;">
              </div>
            </v-img>
          </v-col>
        </template>
      </v-row>
    </v-card>
  </v-container>
</template>
<script setup>
const { smAndUp } = useDisplay()

import hobby1 from '@/assets/images/hob1.png'
import hobby2 from '@/assets/images/hob2.png'
import hobby3 from '@/assets/images/hob3.png'

const items = [{
  title: 'School Class & Records Management System',
  text: 'The frontend stack was constructed with Vue v2, JavaScript, ECMAScript, Vuetify v2, and Vuex v3.',
  link: 'https://github.com/ImCharmainejoy/Iamcj.',
  img: hobby1
},
{
  title: 'Sales Tracker System',
  text: 'The largest free online frontend event. ever.',
  link: 'https://github.com/ImCharmainejoy/Iamcj.',
  img: hobby2
},
{
  title: 'Vaccination System',
  text: 'The frontend stack was constructed with Vue v2, JavaScript, ECMAScript, Vuetify v2, Nuxt v2, and Vuex v3.',
  link: 'https://github.com/ImCharmainejoy/Iamcj.',
  img: hobby3
}]
</script>

<style scoped>
.standalone-img {
  transition: transform 0.4s cubic-bezier(0.4, 0, 0.2, 1), filter 0.4s ease;
  cursor: pointer;
  border-radius: 8px;
  /* Optional: gives it a clean look */
}

.is-hovered {
  transform: scale(1.05);
  filter: brightness(1.1);
}

.transition-opacity {
  transition: opacity 0.3s ease-in-out;
}
</style>
