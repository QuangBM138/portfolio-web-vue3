<template ">
    <section class=" p-16">
        <header class="text-center">
            <h2 class="text-4xl font-bold text-primary dark:text-white">Education</h2>
        </header>
        <ul class="mt-10 space-y-8 y-8">
            <li class="w-full rounded-xl shadow-lg border bg-gradient-to-t to-[#acac39] from-[#1f1e1c99]"
                v-for="(item, index) in Education" :key="index">
                <article class="flex flex-col lg:flex-row items-center lg:items-start rounded-[12px] bg-primary
            mt-[3px] mx-[3px] p-6 md:p-8 lg:p-10">
                    <figure class="w-full lg:w-1/4 flex justify-center lg:justify-start mb-4 lg:mb-0">
                        <Icon icon="hugeicons:university" class="text-4xl md:text-6xl lg:text-7xl text-secondary" />
                    </figure>
                    <section class="w-full lg:w-3/4 lg:pl-4 text-center lg:text-left">
                        <header>
                            <h3 class="text-xl md:text-2xl font-semibold uppercase text-secondary">{{ item.school }}
                            </h3>
                        </header>
                        <p class="text-sm md:text-base text-white">{{ item.degree }}</p>
                        <p class="text-sm md:text-base text-white">{{ item.duration }}</p>

                    </section>
                </article>

            </li>

        </ul>
    </section>
</template>
<script setup lang="ts">
import { Icon } from '@iconify/vue/dist/iconify.js';
import { ref } from 'vue';

interface Education {
    duration: string;
    school: string;
    degree: string;
}

const Education = ref<Education[]>([
    {
        duration: '2018 - 2022',
        school: 'University of Lagos',
        degree: 'BSc. Computer Science'
    },
    {
        duration: '2012 - 2018',
        school: 'Federal Government College',
        degree: 'Senior Secondary School Certificate'
    }
])
</script>
<style scoped></style>