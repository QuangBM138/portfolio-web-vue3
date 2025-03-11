<template>
    <section id="services" class="relative text-white mt-32">
        <SectionHeader title="My Services" />
        <div class="mt-20 py-8 xl:px-16 px-4 sm:py-16 grid grid-cols-1 gap-6 pt-10 sm:grid-cols-2 md:grid-cols-2 
        md:gap-10 md:pt-12 lg:grid-cols-3">
            <article class="px-[12px] mb-[24px]" v-for="element in services" :key="element.id">
                <div class="mt-[30px] relative flex flex-col justify-center text-center rounded-[30px] border
                border-secondary dark:bg-[#ffffff29] bg-primary" data-aos="fade-up" :data-aos-delay="element.id * 100">
                    <div class="mt-[-30px] flex justify-center relative">
                        <div class="mt-[-7px] p-[20px] relative bg-primary rounded-[50%]">
                            <span class="h-[60px] w-[60px] m-auto border-[1px] border-solid border-secondary absolute top-[8px]
                        left-[8px] rounded-[50%] inline-block z-[5]"></span>
                            <img :src="element.icon" alt="services" class="h-[35px] w-[35px] relative z-[1]" />
                        </div>
                    </div>
                    <div class="p-[30px]">
                        <h3 class="uppercase font-semibold text-secondary text-base">
                            {{ element.name }}
                        </h3>
                        <p class="text-[14px] leading-[20px] text-white tracking-[0.03rem]">
                            {{ element.description }}
                        </p>
                    </div>
                </div>
            </article>
        </div>
    </section>
</template>
<script setup lang="ts">
import SectionHeader from '@/components/UI/SectionHeader.vue';
import { ref } from 'vue';

interface services {
    id: number;
    icon: string;
    name: string;
    description: string;
}

const services = ref<services[]>([
    {
        id: 1,
        icon: 'https://img.icons8.com/ios-filled/100/daed1a/google-code.png',
        name: 'Web Development',
        description: 'I can build a website for you'
    },
    {
        id: 2,
        icon: 'https://img.icons8.com/ios-filled/100/daed1a/email-open.png',
        name: 'Mobile Development',
        description: 'I can build a mobile app for you'
    },
    {
        id: 3,
        icon: 'https://img.icons8.com/ios-filled/100/daed1a/windows10-personalization.png',
        name: 'UI/UX Design',
        description: 'I can design a user interface for you'
    },
    {
        id: 4,
        icon: 'https://img.icons8.com/ios-filled/100/daed1a/web-design.png',
        name: 'SEO',
        description: 'I can optimize your website for search engines'
    },
    {
        id: 5,
        icon: 'icon',
        name: 'Digital Marketing',
        description: 'I can market your business online'
    },
    {
        id: 6,
        icon: 'icon',
        name: 'Content Writing',
        description: 'I can write content for your website'
    },
    {
        id: 7,
        icon: 'icon',
        name: 'Graphic Design',
        description: 'I can design graphics for your website'
    },
    {
        id: 8,
        icon: 'icon',
        name: 'Video Editing',
        description: 'I can edit videos for your website'
    },
]);

</script>
<style scoped></style>