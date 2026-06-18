<template>
  <v-card id="experience" prepend-icon="mdi-briefcase-outline" variant="flat" title="Work Experience"
    subtitle="These are some of my notable activities and projects I have worked on during my career.">
    <v-timeline density="compact" side="end" v-for="(item, index) in items" :key="index">
      <v-timeline-item :class="item.class" :dot-color="item.dot_color" :size="item.size" :fill-dot="item.is_fill_dot">
        <template v-slot:icon>
          <span v-if="item.is_fill_dot">{{ item.fill_dot_title }}</span>
        </template>
        <div class="align-start flex-column">
          <div>
            {{ item.company }}
            <v-chip :color="item.company_color" :size="item.company_size" :label="item.is_company_label">
              {{ item.company_duration }}
            </v-chip>
          </div>
          <div>
            {{ item.office_address }}
          </div>
        </div>
      </v-timeline-item>

      <v-timeline-item v-for="(posItem, posIndex) in item.positions" :key="posIndex" :class="posItem.class"
        :dot-color="posItem.dot_color" :size="posItem.size" :fill-dot="posItem.is_fill_dot">
        <div class="align-start flex-column">
          <div>
            {{ posItem.position }}
            <v-chip :color="posItem.duration_color" :size="posItem.duration_size" :label="posItem.is_duration_label">

              {{ posItem.company_duration }}
            </v-chip>
          </div>
          <div>
            {{ posItem.duration }}
          </div>
          <div>
            {{ posItem.department }}
          </div>
        </div>
      </v-timeline-item>
    </v-timeline>

    <v-card variant="flat">
      <v-row align="center" class="fill-height" justify="center">
        <template v-for="(item, i) in activities" :key="i">
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
    <v-card flat color="blue" class="mb-5">
      <v-card-title class="font-style text-h5 text-center">Workshop</v-card-title>
    </v-card>
    <v-row>
      <v-col cols="12" class="mb-0 py-0" v-for="(item, index) in workshops" :key="index">
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
  </v-card>
</template>
<script setup>
import hobby1 from '@/assets/images/act1.png'
import hobby2 from '@/assets/images/act2.png'
import hobby3 from '@/assets/images/act3.png'

const { smAndUp } = useDisplay()

const items = [
  {
    is_fill_dot: true,
    size: 'large',
    dot_color: 'blue',
    class: 'mb-12',
    fill_dot_title: 'IS',
    company: 'Infosoft Studio under Mini Clean Business Solutions',
    company_duration: '7 years 6 months',
    position: 'Chief Software Architect',
    company_color: 'purple',
    company_size: 'small',
    is_company_label: true,
    office_address: 'Davao, Davao Region, Philippines',
    positions: [
      {
        is_fill_dot: false,
        size: 'x-small',
        dot_color: 'white',
        class: 'mb-12',
        position: 'Chief Software Architect',
        company_duration: '1 year 7 months',
        duration: 'Jan 2024 - Present',
        duration_color: 'purple',
        duration_size: 'small',
        is_duration_label: true,
        department: 'Software Development Team'
      },
      {
        is_fill_dot: false,
        size: 'x-small',
        dot_color: 'white',
        class: 'mb-12',
        position: 'Frontend Web Developer',
        company_duration: '6 years 9 months',
        duration: 'Feb 2018 - Oct 2024',
        duration_color: 'purple',
        duration_size: 'small',
        is_duration_label: true,
        department: 'Software Development Team'
      }
    ]
  },

]

const activities = [{
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

const workshops = [{
  icon: 'mdi-briefcase',
  award: 'Participant',
  year: 'March 2018',
  title: 'Spacelap Co-working Space',
  subtitle: 'Participated in a DevCon Davao technical session to stay updated on industry standards and local development practices. Engaged in high-level discussions regarding [Topic such as Scalable Frontend Solutions] and collaborated with peers to share insights on the evolving role of developers in the region.'
},
{
  icon: 'mdi-briefcase',
  award: 'ACSS Member',
  year: 'September 2016',
  title: `iDeya Brew: An Ideation Workshop`,
  subtitle: 'Helped facilitate the successful execution of the iDeya Brew workshop at Cor Jesu College, which strengthened the partnership between the college and MSU-IIT iDeya Speakers.'
}]
</script>