<template>
  <v-card id="about" variant="flat" class="px-2">
    <v-row class="negative-top" align="center">
      <v-col cols="12" sm="12" class="text-center mb-0 pb-0">
        <span class="font-style" :class="smAndUp ? 'text-h4' : 'text-caption'">
          Charmaine Joy Rosatace
        </span>
      </v-col>
      <v-col cols="12" sm="12" class="text-center mt-0 pt-0">
        <span class="font-style font-weight-bold" :class="smAndUp ? 'text-h5' : 'text-caption'">
          Frontend Web Developer
        </span>
      </v-col>
      <v-col cols="12" sm="4" class="text-center">
        <v-avatar :size="smAndUp ? '180' : '100'">
          <v-img :src="myAvatar" alt="Iamcj. Avatar"></v-img>
        </v-avatar>
      </v-col>
      <v-col cols="12" sm="8">
        <p class="text-caption font-style mb-2 text-justify">
          I am writing to express my strong interest in the <strong>Front-end Engineering</strong> position.<br />
        </p>
        <p class="text-caption font-style pb-5 text-justify">
          As a dedicated Computer Science graduate and an experienced frontend developer specializing in the Vue.js
          ecosystem,<br />
          I am eager to bring my technical skills, problem-solving mindset, and enthusiastic work ethic to your
          engineering team.<br />
        </p>
      </v-col>
      <v-col cols="12">
        <p class="text-caption font-style mb-2 text-justify">
          Throughout my journey in web development, I have focused heavily on building clean, performant, and highly
          reactive user interfaces. <br />
          My foundational background in Computer Science allows me to approach UI architecture with structural
          integrity—ensuring that modular components are not only visually seamless but also scalable and
          maintainable.<br />
          Having worked extensively with modern JavaScript frameworks, particularly Vue, I excel at transforming complex
          client requirements and backend APIs into smooth, intuitive end-user experiences.<br />
        </p>
        <p class="text-caption font-style mb-2 text-justify">
          Beyond engineering metrics, my professional drive is deeply rooted in continuous refinement. I am a proud
          Filipina and a relentless dreamer whose ultimate vision is to consistently evolve, grow professionally, and
          become the best version of myself in everything I build.<br />
          I approach each development challenge with a sense of purpose and commitment, viewing software engineering not
          just as a career, but as an opportunity to deliver excellence for the glory of God.<br /> This foundation
          ensures
          that I bring integrity, deep accountability, and an optimistic, collaborative energy to your workplace daily.
          <br />
        </p>
        <p class="text-caption font-style mb-2 text-justify">
          I welcome the opportunity to discuss how my frontend experience and technical background can help advance your
          ongoing projects.<br />
          Thank you for your time, consideration, and review of my application.<br />
        </p>
        <p class="text-caption font-style mb-2 text-justify">
          I look forward to the new environment and a chance to meet and collaborate with new talented
          professionals.<br />
        </p>
      </v-col>
    </v-row>
  </v-card>
</template>
<script setup>
import myAvatar from '@/assets/images/me.png'
const { smAndUp } = useDisplay()
</script>
<style scoped>
.negative-top {
  margin-top: -10px
}
</style>
