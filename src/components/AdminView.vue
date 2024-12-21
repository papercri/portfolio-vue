<template>

  <h3 class="text-center uppercase font-bold mt-10">Add new project</h3>
      <form class="flex flex-wrap justify-between max-w-screen-lg m-auto mt-8">
      <div class="w-5/12 m-2 flex flex-col">
          <label for="pr-title" class="uppercase font-bold text-sm mb">Project title</label>
          <input v-model="title" id="pr-title"  type="text" placeholder="Add project title" class="rounded-md border p-2 text-black">
      </div>
      <div class="w-5/12 m-2  flex flex-col">
        <label for="imgUrl" class="uppercase font-bold text-sm mb">Image URL</label>
        <input v-model="img" id="imgUrl"  type="text" placeholder="Add image url"  class="rounded-md border p-2 text-black">
      </div>
      <div class="w-full mx-2 my-4  flex flex-col">
        <label for="prDescription" class="uppercase font-bold text-sm mb">Project description</label>
        <textarea v-model="description" name="textarea" id="prDescription" rows="3"   class="rounded-md border p-2 text-black"></textarea>
      </div>
      <div class="my-2 flex justify-center w-full">
        <button @click.prevent="handleSubmit"  type="submit" class="border py-2 px-4 rounded-md  text-white transition-all bg-orange-400 hover:bg-orange-300">Submit</button>
      </div> 
      </form>



</template>

<script>
import projects from '@/projects';

export default {
  name: "AdminView",
  data() {
    return {
      title: "",
      img: "",
      description: "",
    };
  },
  methods: {
    handleSubmit() {
      this.$emit("createProject", {
        
        title: this.title,
        img: this.img,
        description: this.description,
        hidden: false,
      });
    },
  },
};
</script>

<style></style>
