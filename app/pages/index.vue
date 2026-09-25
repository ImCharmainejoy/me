<template>
  <div class="main-page-bg">
    <v-container class="skills-wrapper px-2 py-6" fluid>
      <sharedNavigation :items="items" title="CJPR" />
      <v-row justify="center">
        <v-col cols="12" sm="11">
          <about />
        </v-col>
        <v-col cols="12" sm="11">
          <skills />
        </v-col>
        <v-col cols="12" sm="11">
          <projects />
        </v-col>
        <v-col cols="12" sm="11">
          <experience />
        </v-col>
        <v-col cols="12" sm="11">
          <awards />
        </v-col>
        <v-col cols="12" sm="11">
          <hobbies />
        </v-col>
        <v-col cols="12" sm="11">
          <contact />
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script lang="ts" setup>
const items = [
  {
    el: '#about',
    offset: -70,
    icon: 'mdi-account',
    title: 'About Me',
    model: 'About'
  },
  {
    el: '#skill',
    offset: -70,
    icon: 'mdi-tools',
    title: 'Skills',
    model: 'Skills'
  },
  {
    el: '#projects',
    offset: -70,
    icon: 'mdi-post',
    title: 'Projects',
    model: 'Projects'
  },
  {
    el: '#experience',
    offset: -70,
    icon: 'mdi-briefcase-outline',
    title: 'Work Experience',
    model: 'Work Experience'
  },
  {
    el: '#awards',
    offset: -70,
    icon: 'mdi-trophy-award',
    title: 'Awards & Recognitions',
    model: 'Awards & Recognitions'
  },
  {
    el: '#hobbies',
    offset: -70,
    icon: 'mdi-coffee',
    title: 'Hobbies',
    model: 'Hobbies'
  },
  {
    el: '#contact',
    offset: -70,
    icon: 'mdi-email',
    title: 'Contacts',
    model: 'Contacts'
  }
]
</script>

<style scoped>
.main-page-bg {
  background-color: #FAFAFA !important;
  min-height: 100vh;
  width: 100%;
}

.skills-wrapper {
  background-color: #FAFAFA !important;
}
</style>