<template>
    <div id="videos">
        <button @click="pre" v-show="index>0">pre</button>
        <a :href="videos[index].link" target="_blank">
            <img :src="videos[index].src" alt="">
        </a>
        <a :href="videos[index+1].link" target="_blank">
            <img :src="videos[index+1].src" alt="">
        </a>
        <a :href="videos[index+2].link" target="_blank">
            <img :src="videos[index+2].src" alt="">
        </a>
        <button @click="next" v-show="index<videos.length-3">next</button>
    </div>
</template>

<script>
import data from '../data.json'

export default {
    name: 'RecommandVideo',
    data: function() {
        return {
            videos: data.videos,
            index: 0
        }
    },
    methods: {
        pre: function() {
            this.index--;
        },
        next: function() {
            this.index++;
        }
    }
}
</script>

<style>
#videos a img {
    width: 200px;
    height: 200px;
}
</style>