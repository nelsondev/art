<template>
    <v-app >
        <v-main style="background: #050505 !important;">
            <v-container fluid>
                <a class="d-flex align-center white--text" href="https://nelsontron.com" style="text-decoration: none !important;">
                    <v-spacer></v-spacer>
                    <span class="font mr-0" style="font-size: 22pt !important;">NELSON ART ◼</span>
                    <v-img
                    max-width="80pt"
                    max-height="80pt"
                    class="my-3"
                    src="logo.png"
                    ></v-img>
                </a>
                <div class="d-flex flex-wrap">
                    <v-img
                    v-for="(item, i) of images"
                    :key="i"
                    :contain="item.includes('contain')"
                    :src="require(`@/assets/${item}`)"
                    style="image-rendering: pixelated; object-fit: contain"
                    />
                </div>
            </v-container>
        </v-main>
    </v-app>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Patrick+Hand&display=swap');
.font {
    font-family: 'Patrick Hand', cursive;
}
</style>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
    data: () => ({
        images: require.context('@/assets', true, /png|gif|jpg|jpeg/).keys().map(x => x.substr(2, x.length))
    })
})
</script>