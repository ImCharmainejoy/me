<template>
  <v-container class="fill-height px-2" width="100%">
    <sharedNavigation :items="items" title="CJPR" />
    <v-row justify="center">
      <v-col cols="12" sm="11" md="10" lg="8">
        <about />
      </v-col>
      <v-col cols="12" sm="11" md="10" lg="8">
        <skills />
      </v-col>
      <v-col cols="12" sm="11" md="10" lg="8">
        <projects />
      </v-col>
      <v-col cols="12" sm="11" md="10" lg="8">
        <experience />
      </v-col>
      <v-col cols="12" sm="11" md="10" lg="8">
        <awards />
      </v-col>
      <v-col cols="12" sm="11" md="10" lg="8">
        <hobbies />
      </v-col>
      <v-col cols="12" sm="11" md="10" lg="8">
        <contact />
      </v-col>
    </v-row>
  </v-container>
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
  }]
</script>