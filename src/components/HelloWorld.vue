<template>
    <button @click="enableGreyScale = !enableGreyScale">
        Toggle Greyscale
    </button>
    <image-array-viewer :imageUrlArray="imgArray" />
</template>

<script lang="ts">
import { ref, defineComponent, computed } from "vue";
import ImageArrayViewer from "./ImageArrayViewer.vue";

import imageMap from "./content/ImageMap";
import imageMapGreyScale from "./content/ImageMapGreyscale";

export default defineComponent({
    name: "HelloWorld",
    components: {
        ImageArrayViewer,
    },
    setup: () => {
        const enableGreyScale = ref(false);

        // const imgArray = imageMap; // use this instead of computed imgArray to get URL transform working

        const imgArray = computed(() => {
            if (enableGreyScale.value) {
                return imageMapGreyScale;
            }
            return imageMap;
        });

        return { imgArray, enableGreyScale };
    },
});
</script>

<style scoped>
a {
    color: #42b983;
}

label {
    margin: 0 0.5em;
    font-weight: bold;
}

code {
    background-color: #eee;
    padding: 2px 4px;
    border-radius: 4px;
    color: #304455;
}
</style>
