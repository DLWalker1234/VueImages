<template>
    <div>
        <img v-bind:src="image.link" v-for="image in allImages"  />


    </div>
</template>

<script>
import { mapActions, mapGetters } from 'vuex';

export default {
    name: 'ImageList',
    computed: mapGetters(['allImages']),
    methods: mapActions(['fetchImages']),
    created() {
        this.fetchImages();
        
    }
}
</script>

<style>

img {
    width: 200px;
    height: 200px;
}

</style>
