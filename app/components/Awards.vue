<template>
  <v-container id="awards" class="pa-0">
    <v-card flat color="blue" class="mb-5">
      <v-card-title class="font-style text-h5 text-center">Professional Certifications & Awards</v-card-title>
    </v-card>
    <v-card id="awards" variant="flat"
      subtitle="These are some of my notable awards and recognitions I have received for my work and contributions.">

      <v-row>
        <v-col cols="12" class="mb-0 py-0" v-for="(item, index) in awards" :key="index">
          <v-card flat :subtitle="item.title" :title="item.award + ' - ' + item.year">
            <template v-slot:prepend>
              <v-avatar color="blue-darken-2">
                <v-icon :icon="item.icon"></v-icon>
              </v-avatar>
            </template>
            <v-card-text>{{ item.subtitle }}</v-card-text>
          </v-card>
        </v-col>
      </v-row>
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

import awards1 from '@/assets/images/awards1.png'
import awards2 from '@/assets/images/awards2.png'
import awards3 from '@/assets/images/awards3.png'

const items = [{
  title: 'School Class & Records Management System',
  text: 'The frontend stack was constructed with Vue v2, JavaScript, ECMAScript, Vuetify v2, and Vuex v3.',
  link: 'https://github.com/ImCharmainejoy/Iamcj.',
  img: awards1
},
{
  title: 'Sales Tracker System',
  text: 'The largest free online frontend event. ever.',
  link: 'https://github.com/ImCharmainejoy/Iamcj.',
  img: awards2
},
{
  title: 'Vaccination System',
  text: 'The frontend stack was constructed with Vue v2, JavaScript, ECMAScript, Vuetify v2, Nuxt v2, and Vuex v3.',
  link: 'https://github.com/ImCharmainejoy/Iamcj.',
  img: awards3
}]

const awards = [{
  icon: 'mdi-trophy',
  award: 'Silver Medalist',
  year: 'April 2017',
  title: 'PRISAA National Games | Chess Women | Team Event',
  location: 'Iba, Zambales, Philippines',
  subtitle: 'Demonstrated a high degree of physical and mental discipline, maintaining peak performance under intense national competition.'
},
{
  icon: 'mdi-trophy',
  award: 'Gold Medalist',
  year: 'September 2016',
  title: `DACS 2016 Women's Division | Chess Women | Individual & Team Event`,
  location: 'Davao City, Philippines',
  subtitle: 'Distinguished as the regional champion for Davao Association of Catholic Schools (DACS), demonstrating elite-level strategic foresight and analytical problem-solving'
},
{
  icon: 'mdi-trophy',
  award: 'Bronze Medalist',
  year: 'October 2013',
  title: `18th Unigames | Chess Women | Team Event`,
  location: 'Bacolod City, Philippines',
  subtitle: 'This achievement highlights a commitment to rigorous training, peak performance under pressure, and the ability to collaborate effectively within a high-performing team unit to achieve a common objective.'
},
{
  icon: 'mdi-trophy',
  award: 'Bronze Medalist',
  year: 'January 2013',
  title: `Annual Awardee | Individual Achievement`,
  location: 'Sacred Heart Avenue, Davao City, Philippines',
  subtitle: `This honor proves that the greatest strength is a disciplined mind. I’ve learned that whether it's a checkmate or a high grade, victory belongs to those who stay patient, stay focused, and always think before they move.`
},
{
  icon: 'mdi-file-certificate-outline',
  award: 'Microsoft Certified Professional',
  year: 'November 2015',
  title: 'Microsoft Certified Professional',
  location: 'Sacred Heart Avenue, Davao City, Philippines',
  subtitle: 'Demonstrates professional skills and expertise with Microsoft platforms, tools and technologies.'
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
