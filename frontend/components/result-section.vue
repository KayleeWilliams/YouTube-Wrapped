<template>
    <div class="flex flex-row gap-5">
        <div class="flex flex-col lg:w-fit 2xl:w-2/4 bg-pink-300 text-pink-900 col-span-1">
            <!-- Top Bar -->
            <div class="flex flex-row justify-end items-center lg:h-12 2xl:h-12 px-6 bg-pink-900 text-pink-300 ">
                <div class="flex flex-row justify-between w-full">
                    <ball />
                    <ball />
                    <ball />
                    <ball />
                    <ball />
                </div>
                <p class="lg:text-xl 2xl:text-2xl font-bold align-center w-3/4 text-right">YouTube Wrapped</p>
            </div>

            <!-- Content Top -->
            <div class="w-max mt-6 mx-8">
                <div class="flex flex-row gap-12 items-center">
                    <img :src="data[6]" class="w-60 h-60">
                    <div class="flex flex-col text-3xl gap-8">
                        <p> Videos Watched <br><span class="font-bold text-4xl"> {{ data[1] }} </span></p>
                        <p> Minutes Watched <br><span class="font-bold text-4xl"> {{ data[0] }}</span></p>
                    </div>
                </div>
            </div>

            <!-- Content Bottom -->
            <div class="flex flex-row lg:gap-12 2xl:gap-0 items-center pt-6 pb-8 mx-8 ">
                <div class="text-3xl w-1/2 truncate">
                    <p class="font-bold"> Top Channels</p>
                    <li v-for="item in data[2]">
                        {{ item }}
                    </li>
                </div>

                <div class="flex flex-col text-3xl w-1/2 font-bold">
                    <p> Comments <br><span class="font-normal"> {{ data[4] }} </span></p>
                    <p> Videos Liked <br><span class="font-normal"> {{ data[5] }} </span></p>
                    <p> Total Searches <br><span class="font-normal"> {{ data[3] }} </span></p>
                </div>
            </div>
        </div>

        <!-- Colour Selector -->
        <!-- <div>
            <button @click="changeColours">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 stroke-white" fill="none" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" d="M13 9l3 3m0 0l-3 3m3-3H8m13 0a9 9 0 11-18 0 9 9 0 0118 0z" /></svg>
            </button>   
        </div> -->
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
    props: {
        item: Array,
        data: Array,
   
    },
    data: () => {
        return {
            topChannels: [],
        };
    },

})
</script>