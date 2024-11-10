<template>
    <div class="w-1/2 mt-10 ml-36">
        <h1 class="text-2xl font-bold pb-5">Course Content</h1>
        <div class="pb-2 flex justify-between">
            <p class="text-sm">6 sections • 29 lectures • 2h 11m total length</p>
            <p class="text-blue-500 font-bold cursor-pointer" @click="toggleExpandAll">{{ allExpanded ?
                'Collapse AllSections' : 'Expand All Sections' }}</p>
        </div>
        <div id="accordion-open" data-accordion="open">
            <!-- Section Template -->
            <template v-for="(section, index) in sections" :key="index">
                <h2 class="bg-[#F7F9FA] ">
                    <button @click="toggleSection(index)"
                        class="flex items-center justify-between w-full p-3 font-medium text-gray-500 border border-b-0 gap-3">
                        <div class="flex items-center pl-7 gap-3">
                            <svg :class="{ 'rotate-180': openSections.includes(index) }"
                                class="w-3 h-3 transition-transform shrink-0 me-3" aria-hidden="true"
                                xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 10 6">
                                <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round"
                                    stroke-width="2" d="M1 1l4 4 4-4" />
                            </svg>
                            <span class="text-black font-bold">{{ section.title }}</span>
                        </div>
                        <span class="text-sm">{{ section.duration }}</span>
                    </button>
                </h2>
                <div v-if="openSections.includes(index)" class="p-5 flex flex-col gap-y-2 pl-10 underline text-[#A435F0] border">
                    <div class="flex justify-between"><p class="flex items-center gap-2"><svg xmlns="http://www.w3.org/2000/svg" fill="none"
                            viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="size-4 text-black">
                            <path stroke-linecap="round" stroke-linejoin="round"
                                d="m15.75 10.5 4.72-4.72a.75.75 0 0 1 1.28.53v11.38a.75.75 0 0 1-1.28.53l-4.72-4.72M4.5 18.75h9a2.25 2.25 0 0 0 2.25-2.25v-9a2.25 2.25 0 0 0-2.25-2.25h-9A2.25 2.25 0 0 0 2.25 7.5v9a2.25 2.25 0 0 0 2.25 2.25Z" />
                        </svg>
                        {{ section.description }}</p><span>preview</span> <span>02:45</span></div>
                        <div class="flex justify-between"><p class="flex items-center gap-2"><svg xmlns="http://www.w3.org/2000/svg" fill="none"
                            viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="size-4 text-black">
                            <path stroke-linecap="round" stroke-linejoin="round"
                                d="m15.75 10.5 4.72-4.72a.75.75 0 0 1 1.28.53v11.38a.75.75 0 0 1-1.28.53l-4.72-4.72M4.5 18.75h9a2.25 2.25 0 0 0 2.25-2.25v-9a2.25 2.25 0 0 0-2.25-2.25h-9A2.25 2.25 0 0 0 2.25 7.5v9a2.25 2.25 0 0 0 2.25 2.25Z" />
                        </svg>
                        {{ section.description }}</p><span>preview</span> <span>02:45</span></div>
                </div>
            </template>
        </div>
    </div>
</template>

<script setup>
import { ref, computed } from 'vue';
const openSections = ref([]);

// Data for sections
const sections = ref([
    {
        title: 'Overview',
        duration: '2 lectures 8 min',
        description: 'Lecture: Identifying the content needed for your project.',
    },
    {
        title: 'Exercise: Identifying Content Workflows',
        duration: '2 lectures 8 min',
        description: 'Lecture: A hands-on exercise to map out content workflows.',
    },
    {
        title: 'First: My Tips for Successful Information Architecture',
        duration: '2 lectures 8 min',
        description: 'Lecture: Best practices for creating a solid information architecture.',
    },
    {
        title: 'Creating & Prioritizing IA',
        duration: '2 lectures 8 min',
        description: 'Lecture: How to structure and prioritize your information architecture.',
    },
    {
        title: 'Exercise: Determining Information Priority',
        duration: '2 lectures 8 min',
        description: 'Lecture: Exercise to determine and set priorities for your information.',
    },
    {
        title: 'Tools for Creating IA Models',
        duration: '2 lectures 8 min',
        description: 'Lecture: Overview of tools that help in creating information architecture models.',
    },
]);

// Computed property to check if all sections are expanded
const allExpanded = computed(() => openSections.value.length === sections.value.length);

// Function to toggle a section's open state
function toggleSection(index) {
    if (openSections.value.includes(index)) {
        openSections.value = openSections.value.filter((i) => i !== index);
    } else {
        openSections.value.push(index);
    }
}

// Function to toggle expand/collapse all sections
function toggleExpandAll() {
    if (allExpanded.value) {
        // Collapse all sections
        openSections.value = [];
    } else {
        // Expand all sections
        openSections.value = sections.value.map((_, index) => index);
    }
}

</script>
