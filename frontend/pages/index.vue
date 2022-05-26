<template>
    <div class="bg-stone-900 w-screen h-max lg:w-full lg:h-screen grid grid-cols-3 grid-rows-6">
        <div class="bg-stone-900 col-start-2 row-start-1 visible xl:invisible">
            <device-message />
        </div>

        <div v-show="showTitle" class="col-start-2 row-start-2 row-span-3 col-span-1 xl:visible invisible">
            <title-section @hideSection="show" />
        </div>

        <div v-show="showTitle == false & showHow == true" class="col-start-2 row-start-2 row-span-4 col-span-1">
            <how-section @hideSection="show" />
        </div>

        <div v-show="showHow == false & showUpload == true" class="col-start-2 row-start-2 row-span-4 col-span-1">
            <upload-section @fileUpload="sendData" />
        </div> 

        <div class="col-start-2 row-start-1 row-span-4 col-span-2 lg:mt-14 2xl:mt-28">
            <result-section @hideSection="show" :data="uploadResult" v-if="showUpload == false" />
        </div>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
    name: "App",
    components: {},
    data: () => {
        return {
            showTitle: true,
            showHow: true,
            showUpload: true,
            showResult: false,
            uploadResult: [] 
        };
    },
    methods: {
        show(section) {
            if (section == 'title') {
                this.showTitle = false
            }

            if (section == 'how') {
                this.showHow = false
            }

            if (section == 'result') {
                this.showResult = false
            }
        },

        sendData(data) {
            this.showUpload = false,
            this.showResult = true,
            this.uploadResult = data
        }
    }
});


</script>
