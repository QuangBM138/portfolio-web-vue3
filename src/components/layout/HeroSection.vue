<template>
    <section data-aos="zoom-in" class="flex justify-center items-center dark:text-white min-h-screen mt-20 lg:mt-0">
        <header class="absolute w-1/2 aspect-[16/5] -skew-x-12 rounded-full bg-gradient-to-r from-[#00c6cc]
        via-[#785ae4] to-secondary opacity-30 dark:opacity-20 blur-[100px] left-10 top-0 hidden md:block">
        </header>
        <header class="absolute w-1/2 aspect-[16/5] -skew-x-12 rounded-full bg-gradient-to-r from-[#00c6cc]
        via-[#785ae4] to-secondary opacity-30 dark:opacity-20 blur-[100px] left-10 top-0 hidden md:block">
        </header>

        <main class="absolute grid lg:grid-cols-2 grid-cols-1 items-center p-2 lg:p-8">
            <header class="text-center lg:text-left">
                <h1 class="mb-6 text-4xl md:text-5xl lg:text-6xl font-bold">
                    Hi, I'm
                    <span class="text-secondary stroke-text text-sroke-primary dark:text-sroke-secondary">
                        Quang</span>
                </h1>
                <p class="text-lg max-w-xl mx-auto lg:mx-0 font-semibold">
                    I'm a full-stack developer with a passion for building beautiful and functional websites.
                </p>
                <div class=" mt-6 flex justify-center lg:justify-start">
                    <Button label="Hire Me" />
                    <a href="" class="font-semibold text-lg w-[10rem] h-[55px] dark:text-secondary
                    rounded-full ml-2 border-2 dark:border-secondary hover:scale-105 bg-white dark:bg-transparent
                    flex justify-center items-center text-primary border-primary">
                        <Icon icon="line-md:download-loop" class="text-3xl" />
                        <span class="ml-1">Resume</span>
                    </a>
                </div>
            </header>
            <aside class="container flex justify-center lg:justify-end mt-20 lg:mt-0 items-center flex-wrap">
                <figure
                    class="card relative m-[30px] md:w-[380px] md:h-[380px] md:before:w-[400px] 
                    md:before:h-[400px] w-[280px] h-[350px] before:w-[300px] before:h-[300px] before:border-[25px]
                    before:border-primary before:shadow-[7px_7px_21px_primary,_-7px_-7px21px_primary] dark:before:border-secondary dark:before:shadow-[7px_7px_21px_secondary,_-7px_-7px21px_secondary]">
                    <div class="relative w-full h-full bg-cover transform translate-x-[10px] translate-y-[10px]">
                        <img src="https://media.licdn.com/dms/image/v2/D5635AQF59PvcJszo5g/profile-framedphoto-shrink_400_400/B56ZUOWqGoHQAc-/0/1739702575883?e=1742299200&v=beta&t=YQElTF3p5olaF5KGkMoy73lZbdCFWHL-Bv9iv-3lkkQ"
                            alt="Hero image" class="max-w-1/2" loading="lazy" />

                    </div>
                </figure>
            </aside>
        </main>
        <svg class="hidden">
            <filter id="wavy1">
                <feTurbulence x="0" y="0" baseFrequency="0.2" numOctaves="5" seed="1"></feTurbulence>
                <feDisplacementMap in="SourceGraphic" scale="30"></feDisplacementMap>
            </filter>
        </svg>
    </section>
</template>

<script setup lang="ts">

import Button from '@/components/UI/Button.vue';
import { Icon } from '@iconify/vue/dist/iconify.js';

</script>

<style scoped>
.container .card:before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    background: transparent;
    z-index: 1;
}

.container .card:nth-of-type(1):before {
    filter: url(#wavy1);
}
</style>
