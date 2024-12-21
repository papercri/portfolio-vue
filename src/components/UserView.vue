<template>
  <div id="header">
    <HeaderCard :featured></HeaderCard>
  </div>
  <div id="portfolio" class="grid sm:grid-cols-2 grid-cols-1 gap-10 items-center justify-center max-w-screen-lg m-auto  p-5">
    <div v-for="(pr) in projects" :key="pr.id"  class="flex  max-w-screen-lg m-auto justify-start gap-2 items-start w-full relative" >
      <ProjectCard :project="pr"  @deleteCard="deleteCardFinal" @featuredImg="featuredImg">
      
      </ProjectCard>
    </div>
  </div>
</template>

<script>
import ProjectCard from "./projectCard.vue" 
import HeaderCard from "./headerCard.vue"
export default {
  name: "UserView",
  props: ["projects"],
  components:{
    ProjectCard,
    HeaderCard
        },
        data() {
            return {
            featured: this.projects[0],
            };
        },
        methods: {
          featuredImg(project){
            this.featured=project
        },
        deleteCardFinal(id) {
          this.$emit("deleteCardFinal", id);
        },
 
    },
  };
</script>

<style>
</style>
