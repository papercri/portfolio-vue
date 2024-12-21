<template>
  <div class="flex flex-col justify-center items-center my-10">
    <h1 class="mx-auto uppercase text-center my-4 font-bold text-2xl">Mi Portfolio</h1>
   
    <AdminView v-if="isAdmin" @createProject="addProject" />
    <UserView v-else :projects="projects" @deleteCardFinal="deleteCardFinal" />
    <div class="flex justify-center gap-4 mt-5">
      <button  v-if="!isAdmin" @click="isAdmin = true" class="border py-2 px-4 rounded-md bg-cyan-700 hover:bg-cyan-950 text-white transition-all">Add Project</button>
      <button @click="isAdmin = false" class="border py-2 px-4 rounded-md bg-cyan-700 hover:bg-cyan-950 text-white transition-all">Watch Portfolio</button>
    </div>
  </div>
</template>

<script>
import AdminView from "./components/AdminView.vue";
import UserView from "./components/UserView.vue";
import ProjectsDB from "./projects.js";

export default {
  name: "App",
  components: {
    UserView,
    AdminView,
  },
  data() {
    return {
      isAdmin: true,
      count : 5,
      projects: ProjectsDB,
    };
  },
  methods: {
    addProject(project) {
      project.id=this.count;
      this.projects.push(project);
      this.isAdmin=false;
      this.count++;
    },
    deleteCardFinal(id) {
      this.projects = this.projects.filter(pr => pr.id !== id);
    }
   
  },
};
</script>

<style></style>
