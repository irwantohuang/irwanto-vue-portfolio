<script setup lang="ts">
defineProps({
    globalLoader: Boolean
})
import Icon from '../../ui/common/Icon.vue';
import { services } from '../../data/services'
import CardSkeleton from '../Skeleton/CardSkeleton.vue';
import TextSkeleton from '../Skeleton/TextSkeleton.vue';

</script>
<template>

    <div class="mt-8">
        <TextSkeleton :title="true" v-if="globalLoader" />
        <h1 v-else class="text-title text-2xl font-semibold text-primary dark:text-accent">What I Do</h1>


        <CardSkeleton v-if="globalLoader"/>
        <div v-else class="mt-4 grid grid-cols-1 md:grid-cols-2 gap-y-4 gap-x-8">
            <template v-for="service in services" :key="service.id">
                <div class="bg-primary-light dark:bg-primary-dark-400 group shadow-md rounded-md flex items-start p-4 gap-6 transition-all duration-100 ease-in hover:scale-[102%] ">
                    <Icon class="icon-secondary icon-default icon-default-size text-2xl" :icon="service.icon" />

                    <div class="flex flex-col">
                        <h2 class="font-semibold text-lg md:text-base lg:text-lg text-primary dark:text-accent uppercase">{{ service.title }}</h2>
                        <p class="font-normal text-sm md:text-xs lg:text-sm text-justify text-primary-dark-200/85 dark:text-primary-light-300">{{ service.description }}</p>
                    </div>
                </div>
            </template>

        </div>

    </div>

</template>