<template>
  <v-container class="d-flex justify-center py-10" id="contact">
    <v-card id="contact" variant="flat" width="100%" prepend-icon="mdi-email" title="Contacts">
      <div :class="smAndUp ? 'd-flex justify-space-evenly' : 'justify-center'" class="pa-4 align-center ga-4">
        <v-avatar size="100">
          <v-img :src="me" alt="Me"></v-img>
        </v-avatar>

        <div class="mr-2">
          <div class="text-subtitle-2 font-weight-bold global-text-style">Let's Connect</div>
          <div class="text-caption">+63 995 1872 924</div>
          <div class="text-caption">iamcjrosatace@gmail.com</div>
        </div>

        <v-divider v-if="smAndUp" vertical class="mx-5"></v-divider>

        <v-btn icon="mdi-github" variant="text" size="small" class="card-bg-color ma-2"
          href="https://github.com/ImCharmainejoy" target="_blank"></v-btn>
        <v-btn icon="mdi-linkedin" variant="text" size="small" color="blue" class="card-bg-color ma-2"
          href="https://www.linkedin.com/in/charmaine-joy-rosatace-397808105/" target="_blank"></v-btn>
        <v-btn icon="mdi-facebook" variant="text" size="small" color="blue darken-2" class="card-bg-color ma-2"
          href="https://www.messenger.com" target="_blank"></v-btn>
      </div>
    </v-card>
  </v-container>
</template>
<script setup>
const { smAndUp } = useDisplay()
import me from '@/assets/images/office.png'
</script>
<style scoped>
.glass-card {
  background: rgba(255, 255, 255, 0.7) !important;
  backdrop-filter: blur(10px);
  border-radius: 30px !important;
}
</style>