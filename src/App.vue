<template>
    <v-app >
        <v-main style="background: #050505 !important;">
            <v-container>
                <div class="d-flex">
                    <v-spacer></v-spacer>
                    <v-btn
                    href="https://nelsontron.com"
                    target="__blank"
                    style="z-index: 99"
                    text
                    color="#050505"
                    class="pa-6"
                    :ripple="false"
                    >
                        <v-img
                        max-width="32pt"
                        max-height="32pt"
                        src="logo-small.svg"
                        ></v-img>
                    </v-btn>
                </div>
                <div class="d-flex flex-wrap">
                    <v-img
                    v-for="(item, i) of images"
                    :key="i"
                    :contain="item.includes('contain')"
                    :src="require(`@/assets/${item}`)"
                    style="image-rendering: pixelated !important; max-width: 400px;"
                    :style="{ 'min-width': item.includes('contain') ? '300px' : 'auto' }"
                    class="mx-auto"
                    />
                </div>
                <v-row>
                    <v-col
                    
                    cols="12"
                    sm="12"
                    md="4"
                    lg="3"
                    >
                    </v-col>
                </v-row>
            </v-container>
        </v-main>
    </v-app>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
    data: () => ({
        images: require.context('@/assets', true, /png|gif|jpg|jpeg/).keys().map(x => x.substr(2, x.length))
    }),
    mounted() { console.log(this.images)}
})
</script>