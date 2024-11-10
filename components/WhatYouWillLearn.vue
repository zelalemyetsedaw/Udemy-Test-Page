<template>
    <div class="w-1/2 my-10 ml-36">
        <div class="mx-auto p-7  border border-spacing-2">
            <h2 class="text-2xl font-bold mb-6">What You'll Learn</h2>
            <div class="relative grid grid-cols-1 md:grid-cols-2 gap-6">
                <!-- Left Column -->
                <ul class="list-none  space-y-4">
                    <li class="text-sm flex items-center" v-for="(item, index) in leftItemsToShow" :key="index">
                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
                            stroke="currentColor" class="mr-3 size-6">
                            <path stroke-linecap="round" stroke-linejoin="round" d="m4.5 12.75 6 6 9-13.5" />
                        </svg>

                        {{ item }}
                    </li>
                </ul>

                <!-- Right Column -->
                <ul class=" list-inside space-y-4">
                    <li class="text-sm flex gap-2 items-center" v-for="(item, index) in rightItemsToShow" :key="index">
                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
                            stroke="currentColor" class="w-5 h-5">
                            <path stroke-linecap="round" stroke-linejoin="round" d="m4.5 12.75 6 6 9-13.5" />
                        </svg>
                        <span class="">{{ item }} </span>
                    </li>
                </ul>

                <!-- Shadow Effect -->
                <div v-if="!showAll" class="absolute bottom-0 left-0 right-0 h-12 bg-gradient-to-t from-white">
                </div>
            </div>

            <!-- Show More Button -->
            <button v-if="!showAll" @click="toggleShowMore"
                class="mt-6 text-sm font-bold text-[#A435F0] focus:outline-none">
                Show More
            </button>

            <!-- Hide Button -->
            <button v-if="showAll" @click="toggleShowMore"
                class="mt-6 text-sm font-bold text-[#A435F0] focus:outline-none">
                Show Less
            </button>
        </div>
    </div>
</template>

<script setup>

import { ref } from 'vue';

// List of items for each column
const leftItems = [
    "Make sure your content — and its organization — is relevant, appropriate, and useful.",
    "Develop an IA that clearly illustrates the depth of content, its organization, and priority.",
    "Label and organize content in a way that makes sense to users.",
    "Rules and methods for organizing the content and flow of a website, app, or system.",
    "Identify and diagram the content workflows critical to your product’s success.",
    "Work with clients or stakeholders to find out how content should be edited, approved, and published.",
    "Extend an IA to logical structures and naming conventions of the code files that make the product reality.",
];

const rightItems = [

    "Organize the content and flow of any kind of website, app, or system.",
    "The five core types of IA models, and when to use each type.",
    "Five ways to organize and categorize content types that always apply, no matter what you’re creating.",
    "The best way to test and validate your IA with clients, stakeholders, and users.",
    "How to use IA work to develop primary, secondary, global, and local navigation.",
    "How to determine key navigation paths and test their appropriateness.",
    "My tips for rock-solid IA, based on nearly three decades working with the biggest brands in the world.",
];

// State management
const showAll = ref(false);
const initialShowCount = 4;

// Computed lists based on "Show More" state
const leftItemsToShow = computed(() =>
    showAll.value ? leftItems : leftItems.slice(0, initialShowCount)
);
const rightItemsToShow = computed(() =>
    showAll.value ? rightItems : rightItems.slice(0, initialShowCount)
);

// Toggle function
const toggleShowMore = () => {
    showAll.value = !showAll.value;
};


</script>

<style lang="scss" scoped></style>