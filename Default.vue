<script setup>
import { ref } from 'vue'
import {Link} from "@inertiajs/vue3";
const isOpen = ref(true)
const homeItems = ["Dashboard", "Profile", "Messages"];
const openMenu = ref(null);

const toggleMenu = (menu) => {
    openMenu.value = openMenu.value === menu ? null : menu;
};

</script>

<template>
    <div :class="isOpen ? 'pl-48' : 'pl-16'" class="fixed w-full bg-white transition-all duration-300 ease-in-out">
        <div class="flex items-center mx-auto px-4 border-b h-16 border-b-slate-300 shadow-sm">
            <div class="flex w-full">
                <div class="flex items-center">
                    <div>
                        <div class="flex items-center">
                            <button @click="isOpen = !isOpen" class="w-[37.5px] h-[37.5px] rounded-md flex items-center justify-center transition-all duration-200 ease-linear hover:bg-[#F1F5F9]">
                                <svg v-if="isOpen" xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-chevrons-left-icon lucide-chevrons-left stroke-1"><path d="m11 17-5-5 5-5"/><path d="m18 17-5-5 5-5"/></svg>
                                <svg v-else xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-chevrons-right-icon lucide-chevrons-right stroke-1"><path d="m6 17 5-5-5-5"/><path d="m13 17 5-5-5-5"/></svg>
                            </button>

                        </div>
                    </div>
                </div>
                <div class="flex gap-3 ms-auto h-16">
                    <div class="flex items-center">
                        <button class="w-[37.5px] h-[37.5px] rounded-md flex items-center justify-center transition-all duration-200 ease-linear hover:bg-[#F1F5F9]">
                            <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-users-icon lucide-users fill-slate-100 stroke-1"><path d="M16 21v-2a4 4 0 0 0-4-4H6a4 4 0 0 0-4 4v2"/><path d="M16 3.128a4 4 0 0 1 0 7.744"/><path d="M22 21v-2a4 4 0 0 0-3-3.87"/><circle cx="9" cy="7" r="4"/></svg>
                        </button>
                    </div>
                    <div class="flex items-center">
                        <button class="w-[37.5px] h-[37.5px] rounded-md flex items-center justify-center transition-all duration-200 ease-linear hover:bg-[#F1F5F9]">
                            <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-sun-icon lucide-sun fill-slate-100 stroke-1"><circle cx="12" cy="12" r="4"/><path d="M12 2v2"/><path d="M12 20v2"/><path d="m4.93 4.93 1.41 1.41"/><path d="m17.66 17.66 1.41 1.41"/><path d="M2 12h2"/><path d="M20 12h2"/><path d="m6.34 17.66-1.41 1.41"/><path d="m19.07 4.93-1.41 1.41"/></svg>
                        </button>
                    </div>
                    <div class="flex items-center">
                        <button class="w-[37.5px] h-[37.5px] rounded-md flex items-center justify-center transition-all duration-200 ease-linear hover:bg-[#F1F5F9]">
                            <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-bell-ring-icon lucide-bell-ring fill-slate-100 stroke-1"><path d="M10.268 21a2 2 0 0 0 3.464 0"/><path d="M22 8c0-2.3-.8-4.3-2-6"/><path d="M3.262 15.326A1 1 0 0 0 4 17h16a1 1 0 0 0 .74-1.673C19.41 13.956 18 12.499 18 8A6 6 0 0 0 6 8c0 4.499-1.411 5.956-2.738 7.326"/><path d="M4 2C2.8 3.7 2 5.7 2 8"/></svg>
                        </button>
                    </div>
                    <div class="flex items-center text-center">
                        <div class="rounded-full h-8 w-8 border-2 border-slate-100">
                            MB
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
    <div :class="isOpen ? 'w-48' : 'w-16'" class="top-0 bottom-0 fixed z-[60] border-r border-slate-300 transition-all duration-300 ease-in-out">
        <div class="flex justify-center items-center h-16">
            LOGO
        </div>
        <div class="flex items-center flex-col space-y-2 pt-2">
            <div class="flex items-center relative">
                <button  @click="toggleMenu('home')" class="w-8 h-8 rounded-md flex items-center justify-center transition-all duration-200 ease-linear cursor-pointer hover:bg-[#F1F5F9]">
                    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-bell-ring-icon lucide-bell-ring fill-slate-100 stroke-1"><path d="M10.268 21a2 2 0 0 0 3.464 0"/><path d="M22 8c0-2.3-.8-4.3-2-6"/><path d="M3.262 15.326A1 1 0 0 0 4 17h16a1 1 0 0 0 .74-1.673C19.41 13.956 18 12.499 18 8A6 6 0 0 0 6 8c0 4.499-1.411 5.956-2.738 7.326"/><path d="M4 2C2.8 3.7 2 5.7 2 8"/></svg>
                </button>

                <div
                    v-if="openMenu === 'home' && !isOpen"
                    class="absolute left-12 top-0 bg-white shadow-lg p-2"
                >
                    <ul class="space-y-1">
                        <li
                            v-for="item in homeItems"
                            :key="item"
                            class="px-4 py-2 rounded-lg cursor-pointer hover:bg-gray-200"
                        >
                            {{ item }}
                        </li>
                    </ul>
                </div>

            </div>
            <div class="flex items-center">
                <Link class="w-8 h-8 rounded-md flex items-center justify-center transition-all duration-200 ease-linear hover:bg-[#F1F5F9]">
                    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-house-icon lucide-house fill-state-100 stroke-1"><path d="M15 21v-8a1 1 0 0 0-1-1h-4a1 1 0 0 0-1 1v8"/><path d="M3 10a2 2 0 0 1 .709-1.528l7-5.999a2 2 0 0 1 2.582 0l7 5.999A2 2 0 0 1 21 10v9a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2z"/></svg>                </Link>
            </div>
            <div class="flex items-center">
                <Link class="w-8 h-8 rounded-md flex items-center justify-center transition-all duration-200 ease-linear hover:bg-[#F1F5F9]">
                    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-log-in-icon lucide-log-in fill-state-100 stroke-1"><path d="m10 17 5-5-5-5"/><path d="M15 12H3"/><path d="M15 3h4a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2h-4"/></svg>                </Link>
            </div>
            <div class="flex items-center">
                <Link class="w-8 h-8 rounded-md flex items-center justify-center transition-all duration-200 ease-linear hover:bg-[#F1F5F9]">
                    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-settings-icon lucide-settings fill-state-100 stroke-1"><path d="M9.671 4.136a2.34 2.34 0 0 1 4.659 0 2.34 2.34 0 0 0 3.319 1.915 2.34 2.34 0 0 1 2.33 4.033 2.34 2.34 0 0 0 0 3.831 2.34 2.34 0 0 1-2.33 4.033 2.34 2.34 0 0 0-3.319 1.915 2.34 2.34 0 0 1-4.659 0 2.34 2.34 0 0 0-3.32-1.915 2.34 2.34 0 0 1-2.33-4.033 2.34 2.34 0 0 0 0-3.831A2.34 2.34 0 0 1 6.35 6.051a2.34 2.34 0 0 0 3.319-1.915"/><circle cx="12" cy="12" r="3"/></svg>                </Link>
            </div>
        </div>
    </div>
    <div :class="isOpen ? 'ml-48' : 'ml-16'" class="transition-all duration-300 ease-in-out pt-16 bg-slate-100 h-screen">
        <slot />
    </div>
</template>

<style scoped>

</style>
