<template>
    <div id="featuredimg" class="flex-none w-2/4"  >
    <img  :src="project.img" :alt="project.title" class="drop-shadow-md" @click="makeFeatured(project)"/>
    </div>
    <div class="description pl-4 w-2/4 shrink text-left text-sm">
    <h2 id="project-title" class="font-bold uppercase mb-4 text-md">
        {{ project.title }}
    </h2>
    <p id="project-description" >
        {{ project.description }}
    </p>
    </div>
    <button @click="deleteItem(project.id)" class="z-10 hover:text-zinc-950 absolute -top-5 right-0 text-3xl text-zinc-700">𐄂</button>
    
</template>
<script>  
    export default {
        name: "ProjectCard",
        props: ["project"],
        methods: {
            makeFeatured(project){
                this.$emit("featuredImg", project);
            },
            deleteItem(id) {
                this.$emit("deleteCard", id);
            },
    },
    };
</script>
<style>
</style>