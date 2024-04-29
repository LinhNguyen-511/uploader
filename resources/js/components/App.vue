<script setup>
import { ref } from "vue";
import vueFilePond from "vue-filepond";
import FilePondPluginFileValidateType from "filepond-plugin-file-validate-type";
import "filepond/dist/filepond.min.css";

const FilePond = vueFilePond(FilePondPluginFileValidateType);
const pond = ref(null);

function handleFilePondInit() {
    console.log("FilePond has initialized");
    console.log(pond.value);
}
</script>

<template>
    <main>
        <div class="max-w-screen-sm mx-auto flex flex-col gap-10 pt-20">
            <h1 class="text-5xl text-center font-bold">Image Uploader</h1>
            <file-pond
                name="image"
                ref="pond"
                label-idle="Click to choose image, or drag here"
                server="/upload"
                accepted-file-type="image/*"
                @init="handleFilePondInit"
            ></file-pond>
        </div>
    </main>
</template>

<style>
body {
    background-color: #3c2f2f;
    color: #be9b7b;
}
</style>
