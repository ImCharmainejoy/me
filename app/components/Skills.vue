<template>
  <v-card id="skill" variant="flat" class="px-2">
    <v-row wrap>
      <v-col cols="12" sm="12" md="4" v-for="(item, index) in data.items" :key="index">
        <v-chip tonal class="text-h5 font-style my-4 mx-5 card-bg-color">
          {{ item.label }}
        </v-chip>
        <v-card-text class="font-style mb-4">
          <div class="mb-4">
            <div class="text-subtitle-1 font-style mb-3">{{ item.description }}</div>
            <div class="text-caption text--secondary font-style">{{ item.subdescription }}</div>
          </div>
        </v-card-text>
      </v-col>
    </v-row>
    <v-card flat color="blue" class="mb-5">
      <v-card-title class="font-style text-h5 text-center">Core Competencies</v-card-title>
    </v-card>
    <v-row>
      <v-col cols="12" class="mb-0 py-0" v-for="(item, index) in data.competencies" :key="index">
        <v-card-actions class="my-0 py-0">
          <v-icon>mdi-checkbox-outline</v-icon>
          <p class="text-subtitle text--secondary font-style my-0 py-0">{{ item.description }}</p>
        </v-card-actions>
      </v-col>
    </v-row>
  </v-card>
</template>

<script setup lang="ts">
import { ref } from 'vue'

// HTML, CSS, and JavaScript Skillset Overview
const data = ref({
  items: [
    {
      label: '6+',
      description: 'Years of experience in frontend web development',
      subdescription: 'Over six years of hands-on experience with technologies such as Vue, JavaScript and Typescript.',
    },
    {
      label: '2+',
      description: 'Years of project management',
      subdescription: 'As a software architect, I focus on overseeing projects and connecting to clients and other stakeholders.',
    },
    {
      label: '8+',
      description: 'Overall years in the software development industry.',
      subdescription: 'Acquired eight years and counting of skills to enhance my expertise.',
    }
  ],
  competencies: [
    {
      description: 'Equipped with HTML, CSS, JavaScript & Typescript'
    },
    {
      description: 'Equipped with Vue 2 Options API, Vuex, Vue Router,Axios'
    },
    {
      description: 'Knows basic Vue 3 Composition API, Pinia,Vite.'
    },
    {
      description: 'Knowledge of Python'
    },
    {
      description: 'Equipped with Nuxtjs v2 & v3 Routing, Layout & Components'
    },
    {
      description: 'Equipped with Git, Github, Bitbucket for version control'
    },
    {
      description: 'Used ClickUp, Trello, Slack, Discord and Zoom for task management and collaboration'
    },
    {
      description: 'Equipped with making flowcharts and process flows using draw.io and canva'
    },
    {
      description: 'Knowledge of Inertia.js & php/Laravel'
    },
    {
      description: 'Knowledge of Linux / MacOS / Unix-like environments'
    },
    {
      description: 'Knowledge with responsive web app'
    }
  ]
});
</script>

<style scoped>
.xs-container {
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  border-radius: 8px;
  height: 350px;
  /* Give the chart container a fixed height or min-height */
}

.sm-and-up-container {
  max-width: 800px;
  margin: 20px auto;
  padding: 20px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  border-radius: 8px;
  height: 350px;
  /* Give the chart container a fixed height or min-height */
}
</style>