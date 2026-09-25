<template>
  <v-container fluid class="about-wrapper py-10 px-4 px-md-8" id="about">
    <div class="max-width-container mx-auto">
      <v-card class="chic-about-card pa-6 pa-md-10" elevation="1" rounded="xl">
        <v-row align="center" justify="center">
          <!-- Avatar Section with Metallic Ring -->
          <v-col cols="12" md="4" class="text-center mb-4 mb-md-0">
            <div class="avatar-ring-container d-inline-block position-relative">
              <v-avatar :size="smAndUp ? '190' : '130'" class="about-avatar">
                <v-img :src="myAvatar" alt="Charmaine Joy Rosatace"></v-img>
              </v-avatar>

              <!-- Subtle Software Engineer Badge -->
              <div class="avatar-badge">
                <v-icon size="14" color="#B88E30">mdi-code-json</v-icon>
              </div>
            </div>
          </v-col>

          <!-- Bio & Intro Content Section -->
          <v-col cols="12" md="8">
            <!-- Greeting & Name -->
            <div class="mb-4">
              <span class="text-overline gold-accent-text font-weight-bold d-block mb-1">
                Welcome to my portfolio
              </span>
              <h2 class="text-h4 text-md-h3 font-weight-bold text-high-emphasis tracking-wide">
                Hi! I'm <span class="gold-gradient-text">Charmaine Joy Rosatace</span>
              </h2>
            </div>

            <!-- Professional Bio Statements -->
            <div class="bio-text-content text-body-1 text-medium-emphasis">
              <p class="mb-3">
                An enthusiastic and committed professional with a solid background in
                <strong class="text-high-emphasis font-weight-bold">Computer Science</strong>.
              </p>

              <p class="mb-3">
                As a dedicated <strong class="text-high-emphasis font-weight-bold">Frontend Web Developer</strong>,
                I have extensive experience building with <strong>Vue 2</strong>, <strong>JavaScript</strong>, and
                <strong>Nuxt 2</strong>,
                and I am actively mastering modern tools including <strong>Vue 3</strong>, <strong>TypeScript</strong>,
                <strong>Nuxt 3</strong>, <strong>Vite</strong>, and <strong>Pinia</strong>.
              </p>

              <p class="mb-3">
                A <strong class="text-high-emphasis font-weight-bold">Proud Filipina</strong> and a passionate dreamer,
                my vision is to grow professionally from the ground up and continuously strive to be a better version of
                myself—all for the glory of God.
              </p>

              <!-- Language Tags -->
              <div class="d-flex align-center flex-wrap ga-2 pt-2">
                <v-icon size="16" color="#B88E30" class="mr-1">mdi-translate</v-icon>
                <span class="text-caption font-weight-bold text-uppercase text-medium-emphasis mr-2">Languages:</span>

                <v-chip size="small" variant="outlined" class="chic-chip">Tagalog (Native)</v-chip>
                <v-chip size="small" variant="outlined" class="chic-chip">English (Fluent)</v-chip>
                <v-chip size="small" variant="outlined" class="chic-chip">Japanese (Basic)</v-chip>
              </div>
            </div>
          </v-col>
        </v-row>

        <!-- Corner Decorative Paw -->
        <div class="chic-bottom-paw">
          <v-icon size="16" color="#E6D3A3">mdi-paw</v-icon>
        </div>
      </v-card>
    </div>
  </v-container>
</template>

<script setup lang="ts">
import { useDisplay } from 'vuetify'
import myAvatar from '@/assets/images/me.png'

const { smAndUp } = useDisplay()
</script>

<style scoped>
/* Container Setup */
.about-wrapper {
  background-color: #FAFAFA;
}

.max-width-container {
  max-width: 1140px;
}

/* Chic White Card Styling (Matches Skills.vue) */
.chic-about-card {
  background-color: #FFFFFF !important;
  border: 1px solid #EAE5D9 !important;
  box-shadow: 0 10px 30px rgba(184, 142, 48, 0.05) !important;
  position: relative;
  overflow: hidden;
}

/* Typography Highlights */
.gold-gradient-text {
  background: linear-gradient(135deg, #8A6D2B 0%, #C5A059 50%, #8A6D2B 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.gold-accent-text {
  color: #B88E30;
  letter-spacing: 2px !important;
}

.tracking-wide {
  letter-spacing: -0.5px;
}

/* Avatar Border & Ring Accent */
.avatar-ring-container {
  padding: 6px;
  border-radius: 50%;
  background: linear-gradient(135deg, #D4AF37 0%, #E6D3A3 100%);
}

.about-avatar {
  border: 4px solid #FFFFFF;
}

.avatar-badge {
  position: absolute;
  bottom: 8px;
  right: 12px;
  background: #FFFFFF;
  border: 1px solid #EAE5D9;
  border-radius: 50%;
  padding: 6px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.08);
  display: flex;
  align-items: center;
  justify-content: center;
}

/* Bio Text Spacing & Chips */
.bio-text-content {
  line-height: 1.7;
}

.chic-chip {
  border-color: #EAE5D9 !important;
  color: #555555 !important;
  font-weight: 500;
}

/* Corner Paw Accent */
.chic-bottom-paw {
  position: absolute;
  bottom: 12px;
  right: 16px;
  opacity: 0.6;
}
</style>