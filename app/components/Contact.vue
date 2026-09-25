<template>
  <v-container fluid class="contact-wrapper py-10 px-4 px-md-8" id="contact">
    <div class="max-width-container mx-auto">

      <!-- Section Header -->
      <div class="text-center mb-10">
        <h1 class="text-h3 font-weight-bold gold-gradient-text tracking-wide mb-2">
          GET IN TOUCH
        </h1>
        <p class="text-subtitle-1 text-medium-emphasis">
          Feel free to reach out for collaborations, inquiries, or just to say hello.
        </p>
      </div>

      <!-- Main Contact Card -->
      <v-card class="chic-contact-card pa-6 pa-md-8 mx-auto" elevation="1" rounded="xl">
        <div class="d-flex flex-column flex-md-row align-center justify-space-between ga-6">

          <!-- Profile Section -->
          <div class="d-flex flex-column flex-sm-row align-center ga-5 text-center text-sm-left">
            <v-avatar size="96" class="chic-avatar-border">
              <v-img :src="me" alt="Charmaine Joy Rosatace" cover></v-img>
            </v-avatar>

            <div>
              <div class="d-flex align-center justify-center justify-sm-start ga-2 mb-1">
                <v-icon size="16" color="#B88E30">mdi-star-four-points-outline</v-icon>
                <h2 class="text-h6 font-weight-bold text-high-emphasis">
                  Let's Connect
                </h2>
              </div>
              <p class="text-body-2 text-medium-emphasis mb-0">
                Open for opportunities & technical discussions
              </p>
            </div>
          </div>

          <v-divider v-if="mdAndUp" vertical class="my-2 border-opacity-50" color="#EAE5D9"></v-divider>

          <!-- Direct Contact Details -->
          <div class="d-flex flex-column ga-3">
            <a href="tel:+639951872924" class="contact-link d-flex align-center ga-3 pa-2 rounded-lg">
              <v-avatar color="#F8F4EB" size="36" rounded="lg">
                <v-icon size="18" color="#B88E30">mdi-phone-outline</v-icon>
              </v-avatar>
              <span class="text-body-2 font-weight-medium text-high-emphasis">+63 995 1872 924</span>
            </a>

            <a href="mailto:cjrosatace@gmail.com" class="contact-link d-flex align-center ga-3 pa-2 rounded-lg">
              <v-avatar color="#F8F4EB" size="36" rounded="lg">
                <v-icon size="18" color="#B88E30">mdi-email-outline</v-icon>
              </v-avatar>
              <span class="text-body-2 font-weight-medium text-high-emphasis">cjrosatace@gmail.com</span>
            </a>
          </div>

          <v-divider v-if="mdAndUp" vertical class="my-2 border-opacity-50" color="#EAE5D9"></v-divider>

          <!-- Social Buttons -->
          <div class="d-flex align-center justify-center ga-3">
            <v-btn icon="mdi-github" variant="flat" class="chic-social-btn" href="https://github.com/ImCharmainejoy"
              target="_blank" aria-label="GitHub Profile"></v-btn>

            <v-btn icon="mdi-linkedin" variant="flat" class="chic-social-btn"
              href="https://www.linkedin.com/in/charmaine-joy-rosatace-397808105/" target="_blank"
              aria-label="LinkedIn Profile"></v-btn>

            <v-btn icon="mdi-facebook-messenger" variant="flat" class="chic-social-btn" href="https://www.messenger.com"
              target="_blank" aria-label="Messenger Profile"></v-btn>
          </div>

        </div>

        <!-- Subtle Decorative Paw Accent -->
        <div class="chic-bottom-paw">
          <v-icon size="14" color="#E6D3A3">mdi-paw</v-icon>
        </div>
      </v-card>

    </div>
  </v-container>
</template>

<script setup lang="ts">
import { useDisplay } from 'vuetify'
import me from '@/assets/images/office.png'

const { mdAndUp } = useDisplay()
</script>

<style scoped>
/* Container Setup */
.contact-wrapper {
  background-color: #FAFAFA;
}

.max-width-container {
  max-width: 1000px;
}

/* Typography & Colors */
.gold-gradient-text {
  background: linear-gradient(135deg, #8A6D2B 0%, #C5A059 50%, #8A6D2B 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  letter-spacing: 2px !important;
}

/* Main Card Style */
.chic-contact-card {
  background-color: #FFFFFF !important;
  border: 1px solid #EAE5D9 !important;
  box-shadow: 0 10px 30px rgba(184, 142, 48, 0.05) !important;
  position: relative;
  overflow: hidden;
}

.chic-avatar-border {
  border: 2px solid #EAE5D9;
  box-shadow: 0 4px 12px rgba(184, 142, 48, 0.1);
}

/* Direct Contact Interactive Links */
.contact-link {
  text-decoration: none;
  transition: background-color 0.2s ease;
}

.contact-link:hover {
  background-color: #F8F4EB;
}

/* Social Buttons */
.chic-social-btn {
  background-color: #FFFFFF !important;
  color: #B88E30 !important;
  border: 1px solid #EAE5D9 !important;
  transition: transform 0.2s ease, border-color 0.2s ease, background-color 0.2s ease;
}

.chic-social-btn:hover {
  transform: translateY(-3px);
  border-color: #D4AF37 !important;
  background-color: #F8F4EB !important;
}

/* Corner Paw Accent */
.chic-bottom-paw {
  position: absolute;
  bottom: 8px;
  right: 12px;
  opacity: 0.5;
}
</style>