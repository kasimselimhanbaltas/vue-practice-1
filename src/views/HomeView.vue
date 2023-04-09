<template>
  <div class="home container">
    <div v-for="content in contents" :key="content.id">
      {{ content.title }}
    </div>
    <div v-if="err">
      {{ err }}
    </div>
    <div v-for="project in projects" :key="project">
      <div class="project-card">
        <h2>{{ project.projectName }}</h2>
        <p>{{ project.description }}</p>
        <div v-for="image in project.images" :key="image" class="project-images">
            <p>{{ image }}</p>
            <img src="../assets/bg1.jpg " alt="">
            <img :src="url(image)"/>
            <img :src="image"/>
          </div>
        <a :href="project.githubLink">Github</a>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import LoginComponent from '@/components/LoginComponent.vue';
import { ref, reactive, computed, watchEffect, watch, useRoute, useRouter } from 'vue';
import getContentsFetch from "../composables/getContentsFetch"


export default {
  name: 'HomeView',
  components: {
    LoginComponent
  },
  setup() {
    const projects =  [
        {
          projectName: "Baltaş Auto Gallery",
          description: "This is a nice project.",
          images: [
            'c11.jpg',
            'c12.png',
            "../assets/c13.jpg",
            "../assets/img/projectimages/c14.png",
            "../assets/img/projectimages/c15.png",
          ],
          githubLink: "",
        },
        {
          projectName: "Car Gallery Management System",
          description: "This is a nice project.",
          images: [
            "../assets/img/projectimages/cc1.png",
            "../assets/img/projectimages/cc2.png",
            "../assets/img/projectimages/cc3.png",
            "../assets/img/projectimages/cc4.png",
            "../assets/img/projectimages/cc5.png",
            "../assets/img/projectimages/cc6.png",
          ],
          githubLink: "",
        },
        {
          projectName: "Earth Info",
          description: "This is a nice project.",
          images: [
            "../assets/img/projectimages/ei1.png",
            "../assets/img/projectimages/ei2.png",
          ],
          githubLink: "",
        },
        {
          projectName: "Visual Exploration Assistant",
          description: "This is a nice project.",
          images: [
          "../assets/img/projectimages/bg1.png",
          "../assets/img/projectimages/bg2.png",
          "../assets/img/projectimages/bg3.png",
          "../assets/img/projectimages/bg4.png"
          ],
          githubLink: "",
        },
      ]



    return {  projects }
  },
  methods: {

  }
}
</script>
