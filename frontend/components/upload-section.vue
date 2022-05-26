<template>
    <div class="text-white flex flex-col gap-y-16 items-center">
        <p class="text-2xl font-semibold text-center "> Upload your Data <br> <span class="font-normal"> To make this go
                smoothly...</span></p>

        <ol class="list-decimal">
            <li>Ensure the .zip file yo are uploading it has the following files:</li>
             <ol class="list-disc pl-5">
                <li>search-history.html</li>
                <li>watch-history.html</li>
                <li>my-comments.html</li>
                <li>subscriptions.csv</li>
            </ol>
            <li>Remove any unnessary files for a speedy upload, for example any videos.</li>
            <li>Upload the required files as in the .zip format.</li>
        </ol>

        <div class="flex flex-col gap-y-8 items-center">
            <div class="flex flex-row gap-6">
                <input type="file" accept=".zip" id="files" @change="handleFile($event)" hidden />
                <label for="files"
                    class="bg-violet-700 hover:bg-violet-500 text-lg px-6 py-4 rounded-lg drop-shadow-lg"> Select File
                </label>
                
                <button v-on:click="submitFile"
                    class="bg-violet-700 hover:bg-violet-500 text-lg px-6 py-4 rounded-lg drop-shadow-lg flex flex-row items-center"> 
                    <div>
                        <div v-show="isLoading == true" class="rounded-full border-violet-100 border-t-violet-100/0 w-6 h-6 border-4  border-solid animate-spin mr-2"></div>
                    </div>
                    Submit
                </button>

            </div>
            <p class="text-base text-center"> Your data will be deleted straight away. <br>
                The code for this project is publically assessable on
                <a class="text-pink-600 underline" href="https://github.com/KayleeWilliams"> GitHub</a>.
            </p>

        </div>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import axios from 'axios'

export default defineComponent({

    emits: ['uploadData'],

    data: () => {
        return {
            file: '',
            isLoading: false
        };
    },

    methods: {
        handleFile(event) {
            this.file = event.target.files[0];
        },

        submitFile() {
            let formData = new FormData();
            this.isLoading = true;
            formData.append('file', this.file);
            axios.post('http://localhost:5000/uploader',
                formData,
                {
                    headers: {
                        // 'Content-Type': 'multipart/x-data'
                    }
                }
            ).then(response => { this.$emit('fileUpload', response.data) });
        },
    }

})
</script>
