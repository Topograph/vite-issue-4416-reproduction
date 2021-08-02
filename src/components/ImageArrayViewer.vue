<template>
    <div class="wrapper">
        <img v-for="(image, index) in imageUrlArray" :src="image" :key="index" />
    </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
    props: {
        imageUrlArray: Array,
        default: () => []
    },
});
</script>


<style>
.wrapper {
    border: 2px solid red;
    display: flex;
    
}
</style>