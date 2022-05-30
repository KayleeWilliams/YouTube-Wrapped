<template>
    <div class="text-white flex flex-col gap-y-16 items-center">
        <p class="text-2xl font-semibold"> How to download your data </p>
        
        <ol class="list-decimal">
            <li>Head over to <a class="text-pink-600 underline hover:text-pink-400 transistion duration-300 ease-in-out" href="https://takeout.google.com" target=”_blank”> Google Takeout</a>
                and sign in</li>
            <li>Select “YouTube and YouTube Music”</li>
            <li>Hit next step and configure your preferences</li>
            <li>Ensure the file type is .zip and create the export</li>
            <li>Once the export is finished ensure it has the following files:</li>
            <ol class="list-disc pl-5">
                <li>search-history.html</li>
                <li>watch-history.html</li>
                <li>my-comments.html</li>
                <li>subscriptions.csv</li>
            </ol>
            <li>Remove any unnessary files for a speedy upload, for example any videos</li>
            <li>Upload the required files as in the .zip format</li>
        </ol>
        <button-template @hideSection="relay" buttonSection="how" buttonText="Ready?" />
    </div>
</template>

<script setup lang="ts">
// Emits
const emit = defineEmits(['hideSection'])

// Functions
function relay(section) {
    emit('hideSection', section)

}
</script>
