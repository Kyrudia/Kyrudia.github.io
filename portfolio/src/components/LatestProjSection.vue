<template>
    <section class="text-white mt-20" id="projects">
        <div class="px-4 xl:pl-16">
            <div class="mb-4 md:flex md:justify-left xl:pr-16">
                <h2 class="text-4xl font-bold text-white"> Mes derniers Projets</h2>
            </div>
            <ul class="px-4 sm:py-16 xl:pr-16 grid grid-cols-1 gap-6 pt-10 sm:grid-cols-2 md:gap-10 md:pt-12 lg:grid-cols-3"
                data-aos="fade-right">
                <div v-for="project in filteredProjects" :key="project.id">
                    <div class="h-52 md:h-[24rem] rounded-t-xl relative group"
                    :style="{ backgroundImage: 'url(' + project.image + ')', backgroundSize: 'cover' }">                    
                    <div class="overlay items-center justify-center absolute top-0 left-0 w-full h-full bg-[#181818] bg-opacity-0
                    hidden group-hover:flex group-hover:bg-opacity-80 transition-all duration-500
                    ">
                    </div>
                </div>
                <div class="text-white rounded-b-xl mt-1 bg-[#111a3e] shadow-lg border border-[#1f1641] py-6 px-4">
                    <h3 class="text-lg font-semibold uppercase lg:text-xl"> {{ project.title }}</h3>
                    <p class="text-[#ADB7BE]">{{ project.description }}</p>
                    <div class="flex flex-wrap p-2.5">
                        <div v-for="technology in project.technologies" :key="technology" class="text-center ml-1 mt-1 rounded-3xl bg-[#111827]"
                        style="box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1); border: 4px solid #111827;backdrop-filter: blur(9px);-webkit-backdrop-filter: blur(9px);"
                        >
                    <p class="px-1 py-2">{{ technology }}</p>
                    </div>
                    </div>
                </div>
                </div>
            </ul>
        </div>
    </section>
</template>
<script setup>
import { ref, computed } from 'vue';

const Projects = ref([
    {
        id: 1,
        category: 'Développement Web',
        image: 'src/assets/project.png',
        title: 'Projet AREA',
        description: 'Le Projet AREA est une solution numérique permettant de relier plusieurs services utilisés au quotidien (Outlook, Google Drive, OpenAI, ...). Elle offre la possibilité d\'automatiser des tâches prédéfinies afin de faciliter le travail de l\'utilisateur',
        technologies: ['VueJS', 'TypeScript', 'TailwindCSS', 'Flutter', 'NestJS', 'MongoDB'],
        gitURL: '',
        webURL: ''
    },
    {
        id: 1,
        category: 'Développement Web',
        image: 'src/assets/project.png',
        title: 'Projet Netflix Clone',
        description: 'Le Projet Netflix Clone est une réplique de la plateforme de streaming Netflix, permettant de parcourir un catalogue de films et de séries, avec affichage dynamique des contenus via une API, une interface utilisateur inspirée du design original, et une navigation fluide entre les différentes sections.',
        technologies: ['HTML', 'CSS', 'JavaScript', 'TailwindCSS'],
        gitURL: '',
        webURL: ''
    },
]);

const selectedCategory = ref('all');
const filteredProjects = computed(() => {
    if (selectedCategory.value === 'all') {
        return Projects.value;
    }
    return Projects.value.filter(project => project.category.toLocaleLowerCase() === selectedCategory.value.toLocaleLowerCase());
})

</script>
