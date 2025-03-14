<template>
    <section class=" mt-32" id="skills">
        <SectionHeader title="My Skills" />
        <div class="mt-20 flex justify-center">
            <ul class="flex flex-wrap justify-center items-center">
                <li ref="skillRefs" v-for="(element, index) in skills" :key="index"
                    :class="`mx-[15px] rounded-[12px] mb-7 bg-gradient-to-t ${element.bgGradient}`">
                    <div class="rounded-[12px] bg-primary mt-[3px] p-12 md:p-5 text-center">
                        <h3 class="font-bold text-[35px] text-white flex items-center justify-center">
                            <Countup v-if="visibleItems[index]" :endVal="element.percentage" :startVal="0"
                                :duration="2" />
                            %
                        </h3>
                        <p class="font-normal text-[16px]" :style="{ color: element.textColor }">{{ element.title }}

                        </p>
                    </div>
                </li>
            </ul>
        </div>
    </section>
</template>
<script setup lang="ts">
import SectionHeader from "@/components/UI/SectionHeader.vue"
import { ref, onMounted } from "vue"

interface Skill {
    percentage: number
    title: string
    bgGradient: string
    textColor: string
}

const skills = ref<Skill[]>([
    {
        percentage: 90,
        title: "HTML",
        bgGradient: "to-[#f38181] from-[#f06c64] ",
        textColor: "text-white"
    },
    {
        percentage: 85,
        title: "CSS",
        bgGradient: "to-secondary from-[#00c6cc]  ",
        textColor: "text-white"
    },
    {
        percentage: 80,
        title: "JavaScript",
        bgGradient: "to-[#f38181] from-[#f06c64]",
        textColor: "text-white"
    },
    {
        percentage: 75,
        title: "Vue.js",
        bgGradient: "to-secondary from-[#00c6cc]",
        textColor: "text-white"
    }])

//track visibility of items
const visibleItems = ref<boolean[]>(skills.value.map(() => false));
const skillRefs = ref<(Element | null)[]>([]);

//IntersectionObserver logic
onMounted(() => {
    const observer = new IntersectionObserver(
        (entries) => {
            entries.forEach((entry) => {
                if (entry.isIntersecting) {
                    const index = skillRefs.value.indexOf(entry.target);
                    if (index !== -1) {
                        visibleItems.value[index] = true; // Mark items as visible
                    }
                }
            });
        }, {
        threshold: 0.3 // Trigger when 30% of the element is visible
    }
    );
    // observe all skills elements
    skillRefs.value.forEach((element) => {
        if (element) {
            observer.observe(element);
        }
    });
});
</script>
<style scoped></style>