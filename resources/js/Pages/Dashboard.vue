<template>
    <app-layout>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="bg-white overflow-hidden shadow-xl sm:rounded-lg">
                    <div class="bg-white">
                        <div class="max-w-7xl mx-auto py-12 px-4 text-center sm:px-6 lg:px-8 lg:py-24">
                            <div class="space-y-8 sm:space-y-12">
                                <div class="space-y-5 sm:mx-auto sm:max-w-xl sm:space-y-4 lg:max-w-5xl">
                                    <h2 class="text-3xl font-extrabold tracking-tight sm:text-4xl">let's Vote!</h2>
                                    <button v-for="(value, index) in values" :class="{ 'rounded-l-md': index === 0, 'rounded-r-md': index === (values.length - 1)}" type="button" class="relative inline-flex items-center px-4 py-2 border border-gray-300 bg-white text-sm font-medium text-gray-700 hover:bg-gray-50 focus:z-10 focus:outline-none focus:ring-1 focus:ring-indigo-500 focus:border-indigo-500">
                                        {{ value }}
                                    </button>
                                </div>
                                <ul class="mx-auto grid grid-cols-2 gap-x-4 gap-y-8 sm:grid-cols-4 md:gap-x-6 lg:max-w-5xl lg:gap-x-8 lg:gap-y-12 xl:grid-cols-6">
                                    <li v-for="teammate in teammates">
                                        <div class="space-y-4">
                                            <img class="mx-auto h-20 w-20 rounded-full lg:w-24 lg:h-24" :src="teammate.profile_photo_url" alt="">
                                            <div class="space-y-2">
                                                <div class="text-xs font-medium lg:text-sm">
                                                    <h3>{{ teammate.name }}</h3>
                                                    <p class="text-indigo-600">Not voted yet</p>
                                                </div>
                                            </div>
                                        </div>
                                    </li>
                                </ul>
                            </div>
                        </div>

                    </div>
                </div>
            </div>
        </div>

    </app-layout>
</template>

<script>
    import AppLayout from '@/Layouts/AppLayout'

    export default {
        components: {
            AppLayout,
        },

        props: {
            teammates: Array,
            values: {
                type: Array,
                default: function () {
                    return [0,0.5,1,2,3,5,8,13,20,40,100]
                },
            },
        },
    }
</script>
