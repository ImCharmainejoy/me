<template>
  <v-container fluid class="experience-wrapper py-10 px-4 px-md-8" id="experience">
    <div class="max-width-container mx-auto">

      <!-- Section Header -->
      <div class="text-center mb-10">
        <h1 class="text-h3 font-weight-bold gold-gradient-text tracking-wide mb-2">
          WORK EXPERIENCE
        </h1>
        <p class="text-subtitle-1 text-medium-emphasis">
          A summary of my professional journey, roles, and key career milestones.
        </p>
      </div>

      <!-- Experience Timeline Card -->
      <v-card class="chic-experience-card pa-6 pa-md-10 mb-10" elevation="1" rounded="xl">
        <v-timeline density="compact" side="end" align="start" class="custom-timeline">

          <template v-for="(companyItem, index) in items" :key="index">
            <!-- Company Header Node -->
            <v-timeline-item dot-color="#B88E30" size="small" fill-dot class="mb-6">
              <template #icon>
                <v-icon size="14" color="#FFFFFF">mdi-domain</v-icon>
              </template>

              <div class="d-flex flex-column flex-sm-row align-start align-sm-center justify-space-between ga-2 mb-1">
                <h2 class="text-h6 font-weight-bold text-high-emphasis leading-tight">
                  {{ companyItem.company }}
                </h2>
                <v-chip size="small" variant="flat" class="chic-duration-chip font-weight-bold">
                  Total: {{ companyItem.company_duration }}
                </v-chip>
              </div>

              <div class="d-flex align-center text-caption text-medium-emphasis mb-4">
                <v-icon size="14" color="#B88E30" class="mr-1">mdi-map-marker-outline</v-icon>
                <span>{{ companyItem.office_address }}</span>
              </div>

              <!-- Roles / Positions under Company -->
              <div class="roles-container d-flex flex-column ga-6 mt-4 pl-2 pl-md-4">
                <div v-for="(posItem, posIndex) in companyItem.positions" :key="posIndex"
                  class="position-card pa-4 rounded-lg">
                  <div
                    class="d-flex flex-column flex-sm-row align-start align-sm-center justify-space-between ga-2 mb-2">
                    <div class="d-flex align-center ga-2">
                      <v-icon size="18" color="#B88E30">mdi-briefcase-check-outline</v-icon>
                      <h3 class="text-subtitle-1 font-weight-bold text-high-emphasis">
                        {{ posItem.position }}
                      </h3>
                    </div>
                    <v-chip size="x-small" variant="outlined" class="chic-chip">
                      {{ posItem.duration }}
                    </v-chip>
                  </div>

                  <div class="d-flex align-center ga-3 text-caption text-medium-emphasis">
                    <span>
                      <strong class="text-high-emphasis">Department:</strong> {{ posItem.department }}
                    </span>
                    <span>•</span>
                    <span class="gold-accent-text font-weight-medium">
                      {{ posItem.company_duration }}
                    </span>
                  </div>
                </div>
              </div>
            </v-timeline-item>
          </template>

        </v-timeline>

        <!-- Corner Paw Accent -->
        <div class="chic-bottom-paw">
          <v-icon size="14" color="#E6D3A3">mdi-paw</v-icon>
        </div>
      </v-card>

      <!-- Notable Activities & Highlights Subsection -->
      <div class="mt-12">
        <div class="d-flex align-center justify-center ga-2 mb-6">
          <v-icon color="#B88E30" size="20">mdi-star-four-points-outline</v-icon>
          <h2 class="text-h5 font-weight-bold text-high-emphasis tracking-wide text-center">
            CAREER HIGHLIGHTS & ACTIVITIES
          </h2>
          <v-icon color="#B88E30" size="20">mdi-star-four-points-outline</v-icon>
        </div>

        <v-row justify="center">
          <v-col v-for="(activity, i) in activities" :key="i" cols="12" sm="6" md="4" class="d-flex">
            <v-card class="chic-activity-card flex-grow-1 pa-4 d-flex flex-column" elevation="1" rounded="xl">
              <v-hover v-slot="{ isHovering, props }">
                <v-img v-bind="props" :src="activity.img" height="200" cover
                  class="rounded-lg position-relative overflow-hidden mb-4">
                  <!-- <div :class="isHovering ? 'opacity-100' : 'opacity-0'"
                    class="overlay-panel d-flex align-center justify-center transition-opacity">
                    <v-btn variant="flat" color="#B88E30" class="text-white font-weight-bold text-caption" rounded="lg"
                      size="small" :href="activity.link" target="_blank" prepend-icon="mdi-github">
                      View Details
                    </v-btn>
                  </div> -->
                </v-img>
              </v-hover>

              <h3 class="text-subtitle-1 font-weight-bold text-high-emphasis mb-2 leading-tight">
                {{ activity.title }}
              </h3>

              <p class="text-body-2 text-medium-emphasis flex-grow-1 mb-0">
                {{ activity.text }}
              </p>

              <!-- Subtle Paw Accent -->
              <div class="chic-bottom-paw">
                <v-icon size="12" color="#E6D3A3">mdi-paw</v-icon>
              </div>
            </v-card>
          </v-col>
        </v-row>
      </div>

    </div>
  </v-container>
</template>

<script setup lang="ts">
import { ref } from 'vue'

import hobby2 from '@/assets/images/act2.png'
import hobby3 from '@/assets/images/act3.png'
import meeting from '@/assets/images/meeting.jpg'
import meeting2 from '@/assets/images/meeting2.jpg'

const items = ref([
  {
    company: 'Infosoft Studio under Mini Clean Business Solutions',
    company_duration: '7 yrs 6 mos',
    office_address: 'Davao, Davao Region, Philippines',
    positions: [
      {
        position: 'Chief Software Architect',
        company_duration: '1 yr 7 mos',
        duration: 'Jan 2024 - Present',
        department: 'Software Development Team'
      },
      {
        position: 'Frontend Web Developer',
        company_duration: '6 yrs 9 mos',
        duration: 'Feb 2018 - Oct 2024',
        department: 'Software Development Team'
      }
    ]
  }
])

const activities = ref([
  {
    title: 'Client Meeting & User Training Session',
    text: 'Facilitated technical client meetings and conducted end-user training sessions to ensure smooth system onboarding, gathering direct feedback to refine software requirements.',
    link: '',
    img: meeting
  },
  {
    title: 'Client Meeting & Project Deployment Discussion',
    text: 'Collaborated with clients and cross-functional teams to outline deployment strategies, evaluate release readiness, and ensure smooth, zero-downtime production launches.',
    link: '',
    img: meeting2
  },
  {
    title: 'Project Presentation & Demo Session',
    text: 'Delivered comprehensive live product demonstrations and technical project presentations to stakeholders, showcasing core application capabilities, architecture, and key business solutions.',
    link: '',
    img: hobby3
  }
])
</script>

<style scoped>
/* Container Setup */
.experience-wrapper {
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

/* Timeline Customization */
.custom-timeline :deep(.v-timeline-item__body) {
  padding-start: 16px !important;
}

/* Main Cards */
.chic-experience-card,
.chic-activity-card {
  background-color: #FFFFFF !important;
  border: 1px solid #EAE5D9 !important;
  box-shadow: 0 10px 30px rgba(184, 142, 48, 0.05) !important;
  position: relative;
  overflow: hidden;
  transition: transform 0.3s cubic-bezier(0.25, 0.8, 0.25, 1), box-shadow 0.3s ease;
}

.chic-activity-card:hover {
  transform: translateY(-6px);
  box-shadow: 0 16px 36px rgba(184, 142, 48, 0.12) !important;
  border-color: #D4AF37 !important;
}

/* Nested Position Block Styles */
.position-card {
  background-color: #F8F4EB;
  border: 1px solid #EAE5D9;
}

/* Badges & Chips */
.chic-duration-chip {
  background-color: #F8F4EB !important;
  color: #8A6D2B !important;
  border: 1px solid #EAE5D9;
}

.chic-chip {
  border-color: #EAE5D9 !important;
  color: #555555 !important;
  background-color: #FFFFFF !important;
  font-weight: 500;
}

/* Activity Images Overlay */
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
  bottom: 10px;
  right: 14px;
  opacity: 0.5;
}
</style>