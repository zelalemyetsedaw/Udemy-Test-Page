<template>
    <div>
        <div class="ml-36 w-1/2 pt-5">
                <h1 class="text-2xl text-bold pb-5"> Requirements </h1>
                <ul class="list-disc list-outside"><li class="ml-5">
                    Nothing. I speak plainly and I deal in reality; no technical terms, jargon or unnecessary acronyms
                    here. This
                    course is for anyone already creating digital products, and anyone completely new to all of it!
            
                </li></ul>
            </div>

            <div class="ml-36 w-1/2 pt-5 mb-20">
                <h1 class="text-2xl text-bold"> Description</h1>
                <div>
                    <div class="relative mx-auto mt-5 text-sm">
                        <!-- Main content container -->
                        <div class="overflow-hidden transition-all duration-300 relative"
                            :class="{ 'max-h-40': !isExpanded }" ref="content">
                            <!-- Paragraphs of content -->
                            <p class="mb-4">
                                Without good, relevant content, there’s no compelling reason for anyone to visit or use
                                the site or
                                app;
                                without clear, understandable structure, no one can find anything! How pages or screens
                                are divided
                                and
                                categorized is a direct result of Information Architecture (IA). What shows up in your
                                navigation
                                menus
                                and
                                interactive controls is a result of IA.
                            </p>
                            <p class="mb-4">
                                Your physical body can’t perform any task without the bones under your muscles and skin,
                                which are
                                designed to
                                support those actions. In the same way, a site, app or system can’t deliver anything to
                                anyone
                                unless
                                its bone
                                structure — it’s Information Architecture — is specifically designed to support those
                                tasks.
                            </p>
                            <p class="mb-4">
                                Information Architecture Fundamentals walks you through everything you need to know —
                                from
                                determining
                                what
                                content should be presented to what it’s called to how it’s organized and what format
                                it’s delivered
                                in.
                                Taken
                                from Joe Natoli's popular UX & Web Design Master Course taken by more than 7,000
                                students, these
                                laser-focused
                                lessons will show you how to:
                            </p>
                            <ul class="list-disc list-inside mb-4">
                                <li>Develop an IA that clearly illustrates the depth of content, its organization, and
                                    priority.
                                </li>
                                <li>Label and organize content in a way that makes sense to users.</li>
                                <li>Rules and methods for organizing the content and flow of a website, app, or system.
                                </li>
                                <li>Identify and diagram the content workflows critical to your product’s success.</li>
                                <li>Work with clients or stakeholders to find out how content should be edited,
                                    approved, and
                                    published.
                                </li>
                            </ul>
                            <p class="mb-4">
                                The five core types of IA models, and when to use each type. Five ways to organize and
                                categorize
                                content
                                types that always apply, no matter what you’re creating. The best way to test and
                                validate your IA
                                with
                                clients, stakeholders, and users. How to use IA work to develop primary, secondary,
                                global, and
                                local
                                navigation.
                            </p>
                            <p class="mb-4 font-bold">
                                Who this course is for: Anyone responsible for the success of digital products (apps,
                                sites,
                                systems) —
                                designers, developers, UX professionals, content professionals, marketing folks, project
                                managers,
                                and
                                product
                                owners.
                            </p>

                            <!-- Shadow effect on the last sentences -->
                            <div v-if="!isExpanded"
                                class="absolute bottom-0 left-0 w-full h-10 bg-gradient-to-t from-white to-transparent">
                            </div>
                        </div>

                        <!-- Show More / Show Less button -->
                        <button @click="toggleContent" class="mt-4 px-4 py-2 text-blue-500 font-semibold">
                            {{ isExpanded ? 'Show Less' : 'Show More' }}
                        </button>
                    </div>
                </div>
    </div>
</div>
</template>

<script setup>
// State for open sections (array to allow multiple sections open at once)

const isExpanded = ref(false);

// Function to toggle the expanded state
function toggleContent() {
    isExpanded.value = !isExpanded.value;
}
</script>

<style lang="scss" scoped>

</style>