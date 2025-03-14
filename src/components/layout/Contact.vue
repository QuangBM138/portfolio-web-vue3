<template>
    <section class="mt-32" id="contact">
        <SectionHeader title="Contact Me" />
        <div class="py-8 lg:py-16 px-4 mx-auto max-w-screen-md">
            <form class="space-y-8">
                <div v-for="(input, index) in form" :key="index">
                    <Input :id="input.id" :label="input.label" :type="input.type" :placeholder="input.placeholder"
                        :rows="input.rows" />
                </div>
                <div class="flex justify-between">
                    <Button label="Send" />
                    <div class="mt-2 flex justify-center space-x-3 md:space-x-8">
                        <a href="https://www.facebook.com/hikarunakirigumi/" target="_blank"
                            class="text-gray-600 hover:text-blue-500">
                            <Icon icon="fa-brands:facebook" style="font-size:2rem" />
                        </a>
                        <a href="linkedin.com/in/bui-quang-65b277295" target="_blank"
                            class="text-gray-600 hover:text-blue-700">
                            <Icon icon="fa-brands:linkedin" style="font-size:2rem" />
                        </a>
                        <a href="https://github.com/QuangBM138" target="_blank"
                            class="text-gray-600 hover:text-blue-800">
                            <Icon icon="fa-brands:github" style="font-size:2rem" />
                        </a>
                    </div>
                </div>
            </form>
        </div>
    </section>
</template>
<script setup lang="ts">
import SectionHeader from '@/components/UI/SectionHeader.vue';
import Input from '@/components/UI/Input.vue';
import Button from '@/components/UI/Button.vue';


interface form {
    id: string;
    label: string;
    type: string;
    placeholder: string;
    rows?: number;
}

const form: form[] = [
    {
        id: 'email',
        label: 'Your Email',
        type: 'text',
        placeholder: 'Enter your email',
        rows: undefined
    },
    {
        id: 'subject',
        label: 'Subject',
        type: 'subject',
        placeholder: 'Enter your subject',
        rows: 6
    },
    {
        id: 'message',
        label: 'Message',
        type: 'textarea',
        placeholder: 'Enter your message',
        rows: 6
    }
]

</script>

<style scoped></style>