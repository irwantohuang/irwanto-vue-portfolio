<script setup lang="ts">
import { experience } from '../../data/experience'
import TextSkeleton from '../Skeleton/TextSkeleton.vue';

defineProps({
    globalLoader: Boolean
})
</script>

<template>
    <div class="mt-8 py-2">
        <TextSkeleton v-if="globalLoader" :title="true" />
        <h1 v-else class="text-title text-2xl font-semibold text-primary dark:text-accent">Experiences</h1>

        <div class="mt-6 flex flex-col gap-2">
            <div v-for="exp in experience" :key="exp.id" class="p-4 rounded transition-all duration-150 hover:bg-primary-light hover:-translate-y-1 hover:shadow-md dark:hover:bg-primary-dark-400">
                <div class="flex sm:flex-row sm:items-center justify-between flex-col items-start">
                    <div class="flex items-center gap-6">
                        <div class="flex items-center justify-center h-12 w-12 rounded bg-primary text-primary-light dark:bg-accent">
                            <fa-icon :icon="exp.icon" class="text-2xl"/>
                        </div>
                        <div class="flex flex-col gap-1 whitespace-nowrap">
                            <span class="font-medium text-primary dark:text-accent">{{ exp.company }}</span>
                            <span class="font-normal text-primary-dark-200/75 dark:text-primary-light-200/75">{{ exp.position }}</span>
                        </div>
                    </div>
                    <div class="mt-2 sm:mt-0">
                        <span class="font-medium text-sm sm:text-base text-primary-dark/50 dark:text-primary-light/50">{{ exp.startDate }} - {{ exp.endDate }}</span>
                    </div>
                </div>
            </div>
        </div>

        <!-- <div class="mt-6 border-l-2 border-black dark:border-primary-light pt-4 pb-2 md:max-w-md lg:max-w-lg">
            <div v-for="exp in experience" :key="exp.id" class="mb-8 relative flex items-start flex-col gap-6">
                <fa-icon icon="fa-solid fa-circle" class="absolute -left-[9px] top-1" />
                <div class="pl-8 flex flex-col w-full">

                    <div class="flex items-center justify-between w-full">
                        <template v-if="globalLoader">
                            <TextSkeleton v-for="n in 2" :key="n" class="w-1/2 h-0" :text="true" />
                        </template>
                        <template v-else>
                            <h2 class="font-semibold text-primary-dark-200 dark:text-primary-light-200 text-base uppercase">{{ exp.position }}
                            </h2>
                            <p class="text-sm italic text-primary-dark/85 dark:text-primary-light-300 text-right">{{ exp.startDate }} - {{ exp.endDate }}</p>
                        </template> 
                    </div>

                    <TextSkeleton class="w-2/3 h-0" v-if="globalLoader" :text="true"/>
                    <h3 v-else class="font-medium text-base text-accent-200 dark:text-accent">{{ exp.company }}</h3>
                </div>
            </div>
        </div> -->
    </div>
</template>