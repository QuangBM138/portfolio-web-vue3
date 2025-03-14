<template>
    <section id="projects" class="relative w-11/12 px-16 mx-auto">
        <SectionHeader title="Projects" />
        <!-- custom navigation Buttons-->
        <button class="swiper-prev absolute top-2/3 left-4 transform 
            -translate-y-1/2 z-10 text-white dark:bg-secondary bg-primary p-4 rounded-full">
            <Icon icon="line-md:arrow-left" class=" font-bold text-3xl" />
        </button>
        <button class="swiper-next absolute top-2/3 right-4 transform 
            -translate-y-1/2 z-10 text-white dark:bg-secondary bg-primary p-4 rounded-full">
            <Icon icon="line-md:arrow-right" class=" font-bold text-3xl" />
        </button>
        <!-- Swiper component -->
        <Swiper :effect="'coverflow'" grabCursor centeredSlides :slidesPerView="'auto'" :coverflowEffect="{
            rotate: 50,
            stretch: 0,
            depth: 100,
            modifier: 1,
            slideShadows: true,
        }" :navigation="navigationOptions" loop pagination :modules="[EffectCoverflow, Navigation]"
            class="max-w-full mt-32">
            <SwiperSlide class="max-w-[300px]" v-for="(project, index) in projects" :key="index">
                <ProjectCard :title="project.title" :description="project.description" :image="project.image"
                    :tags="project.tags" :livelink="project.livelink" :codelink="project.codelink" />
            </SwiperSlide>
        </Swiper>
    </section>
</template>
<script setup lang="ts">
import SectionHeader from '@/components/UI/SectionHeader.vue';
import ProjectCard from '@/components/UI/ProjectCard.vue';
import 'swiper/css'
import 'swiper/css/effect-coverflow'
import 'swiper/css/navigation'
import 'swiper/css/pagination'
import { Swiper, SwiperSlide } from 'swiper/vue';
import { EffectCoverflow, Navigation } from 'swiper/modules';
import { ref } from 'vue';

//define navigation options
const navigationOptions = {
    prevEl: '.swiper-prev',
    nextEl: '.swiper-next',
}

interface Project {
    title: string;
    description: string;
    image: string;
    tags: string[];
    livelink: string;
    codelink: string;
}

const projects = ref<Project[]>([
    {
        title: 'Project 1',
        description: 'Project 1 Description',
        image: 'https://swiperjs.com/demos/images/nature-1.jpg',
        tags: ['HTML', 'CSS', 'JavaScript'],
        livelink: '/',
        codelink: "/"
    },
    {
        title: 'Project 1',
        description: 'Project 1 Description',
        image: 'https://swiperjs.com/demos/images/nature-2.jpg',
        tags: ['HTML', 'CSS', 'JavaScript'],
        livelink: '/',
        codelink: "/"
    },
    {
        title: 'Project 1',
        description: 'Project 1 Description',
        image: 'https://swiperjs.com/demos/images/nature-3.jpg',
        tags: ['HTML', 'CSS', 'JavaScript'],
        livelink: '/',
        codelink: "/"
    },
    {
        title: 'Project 1',
        description: 'Project 1 Description',
        image: 'https://swiperjs.com/demos/images/nature-4.jpg',
        tags: ['HTML', 'CSS', 'JavaScript'],
        livelink: '/',
        codelink: "/"
    },
    {
        title: 'Project 1',
        description: 'Project 1 Description',
        image: 'https://swiperjs.com/demos/images/nature-5.jpg',
        tags: ['HTML', 'CSS', 'JavaScript'],
        livelink: '/',
        codelink: "/"
    },
    {
        title: 'Project 1',
        description: 'Project 1 Description',
        image: 'https://swiperjs.com/demos/images/nature-6.jpg',
        tags: ['HTML', 'CSS', 'JavaScript'],
        livelink: '/',
        codelink: "/"
    },
])

</script>


<style scoped>
.swiper-button-prev,
.swiper-button-next {
    cursor: pointer;
}

.swiper-slide {
    display: flex;
    justify-content: center;
    align-items: center;
}
</style>