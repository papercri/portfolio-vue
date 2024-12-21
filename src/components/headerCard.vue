<template>
    <div class="flex  max-w-screen-lg m-auto justify-center content-stretch gap-2 my-10">
      <div id="h-featuredimg" class="flex-none ">
        <img :src="featured.img" :alt="featured.title" class="superimagen drop-shadow-sm "/>
      </div>
      <div class="description pl-10 w-5/12 shrink">
        <h2 id="h-project-title" class="font-bold uppercase mb-4">
          {{ featured.title }}
        </h2>
        <p id="h-project-description" class="">
          {{ featured.description }}
        </p>
      </div>
    </div>
  </template> 
<script>
  export default {
      name: "HeaderCard",
      props: ["featured"],
  }
</script>
<style>

</style>