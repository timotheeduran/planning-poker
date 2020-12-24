<template>
    <app-layout>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="bg-white overflow-hidden shadow-sm sm:rounded-lg">
                        <div class="max-w-7xl mx-auto py-12 px-4 text-center sm:px-6 lg:px-8 lg:py-24">
                            <div class="space-y-8 sm:space-y-12">
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
                                <div class="max-w-7xl mx-auto py-9 px-4 sm:px-6 lg:px-8">
                                    <div class="bg-indigo-700 rounded-lg shadow-2xl overflow-hidden">
                                        <div class="pt-10 pb-12 px-6 sm:pt-16 sm:px-16 lg:py-16 lg:pr-0 xl:py-20 xl:px-20">
                                            <div class="lg:self-center">
                                                <h2 class="text-3xl font-extrabold text-white sm:text-4xl">
                                                    <span class="block">Let's vote!</span>
                                                </h2>
                                                <button v-for="value in values" type="button" class="mt-3 mr-1 inline-flex items-center px-6 py-3 shadow-sm text-base font-medium rounded-md text-gray-700 bg-white hover:bg-indigo-100 hover:shadow-lg focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500">
                                                    <strong>{{ value }}</strong>
                                                </button>
                                            </div>
                                        </div>
                                    </div>
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
