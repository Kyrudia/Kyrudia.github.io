<template >
    <section class="text-white mt-18" id="about">
        <div class="absolute z-0 top-[93rem] inset-x-0 h-64 flex items-start">
            <div class="h-24 w-64 bg-gradient-to-br from-primary via-secondary blur-2xl to-[#570cac] opacity-20"></div>
        </div>
        <div class="md:grid md:grid-cols-2 gap-8 items-center py-8 px-4 xl:gap-16 sm:py-16 xl:px-16 z-1">
            <div data-aos="flip-right">
                <h2 class="text-4xl font-bold text-white text-left mb-8">Mes Formations</h2>
                <div class="space-y-8 py-8">
                    <div v-for="element in education" :key="element.id"
                    class="flex items-center md:w-[80%] w-full rounded-xl bg-[#111a3e] shadow-lg border border-[#1f1641] h-32"
                    >
                        <div class="w-1/4 flex justify-center">
                            <img src="https://img.icons8.com/ios-glyphs/60/ffffff/graduation-cap--v1.png" class="" alt="graduation-cap--v1">
                        </div>
                        <div class="w-3/4 pl-4">
                            <h3 class="text-2xl font-semibold uppercase text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary lg:text-xl">
                                {{ element.School }}
                            </h3>
                            <p class="text-white">{{ element.program }}</p>
                            <p class="text-white">{{ element.year }}</p>
                        </div>
                    </div>
                </div>
            </div>
            <div class="mt-4 md:mt-0 text-left flex flex-col z-10 h-full" data-aos="flip-right">
                <h2 class="text-4xl font-bold text-white md:text-center text-left mb-4">Plus d' 
                    <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">informations</span>
                    sur moi
                </h2>
                <p class="text-base lg:text-lg mt-8 py-8"> 
                    Depuis le lycée, j’ai toujours été passionné par la programmation.
                    Ce qui n'était au départ qu’un simple intérêt est devenu une véritable vocation au fil des années. 
                    Aujourd’hui, je souhaite me spécialiser dans le développement Web, et plus particulièrement dans le front-end, où je peux combiner ma logique de développeur avec ma créativité. 
                    J’aime concevoir des interfaces attrayantes, intuitives et réactives, et je suis constamment en quête de nouvelles compétences pour créer des expériences utilisateurs engageantes et modernes.
                </p>
            </div>
        </div>
    </section>
</template>
<script setup>
import { ref } from 'vue';
const education=ref([
    {
        id:1,
        School:'Epitech',
        program: 'Titre d\'expert en technologies de l\'information RNCP niveau 7',
        year:'2022-2027'
    },
    {
        id:2,
        School:'Lycée Joseph-Marie Carriat',
        program:'Baccalauréat Sciences et Technologies du Management et de la Gestion',
        year:'2021-2022'
    }
])
</script>
