<script setup lang="ts">
import Header from '../components/Layout/Header.vue';
import SideBar from '../components/Layout/SideBar.vue';
import MainView from './MainView.vue';

</script>

<template>
    <main class="max-w-[1920px] relative z-30 h-screen">

        <div class="container relative mx-auto py-[25px] md:py-[35px] lg:py-[50px] h-full">
            <div class="flex gap-4 h-full">
                <SideBar />

                <div class="relative flex flex-col gap-2 lg:gap-4 h-full w-full">
                    <Header />
                    <MainView />
                </div>
            </div>

        </div>

    </main>

</template>