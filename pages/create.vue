<script>
import { ref } from 'vue';
import MdEditor from 'md-editor-v3';
import 'md-editor-v3/lib/style.css';

const text = ref('# Hello Editor')
</script>

<template>
    <div>
        <p>Create Page</p>
        <NuxtLink to="/documentation" class="nuxtlink">
            Go to documentation
        </NuxtLink>

        <div class="newPost flex justify-center">
            <form @submit.prevent="check">
                <div class="mb-6">
                    <label for="base-input" class="block mb-2 text-sm font-medium text-gray-900 dark:text-gray-300">Title</label>
                    <input type="text" v-model="title" id="base-input" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500">
                </div>

                <md-editor v-model="text" preview-only />

                <label for="content" class="block mb-2 mt-10 text-sm font-medium text-gray-900 dark:text-gray-400">Content</label>
                <v-md-editor v-model="content" height="70vh" placeholder="Post content..."
                    right-toolbar="preview sync-scroll"
                    left-toolbar="undo redo clear | h bold italic strikethrough quote | ul ol table hr | link image code | emoji ">
                    </v-md-editor>
                    <div class="file-container">
                    <input type="file"  @change="uploadFile" multiple id="file-input" accept="image/png, image/jpeg" placeholder=""/>
                    <div class="flex items-center">
                        <button id="saveBtn">
                        Submit
                        </button>
                        <label  id="file" for="file-input">Import file</label>
                        <p id="noFile">No image</p>
                    </div>
                    <div id="images">
                    </div>
                    </div>
                </form>
        </div>
    </div>
</template>

<style>
.nuxtlink {
    color: blue;
}
</style>