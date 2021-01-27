<template>
    <div>
        <v-btn v-if="image" :key="image.id" @click="showTwo" :src="image.src" >Kleuren</v-btn>  
        <v-btn v-if="image" :key="image.id" @click="showOne" :src="image.src">Automerken </v-btn>
    </div>
        
    <img v-if="image" :key="image.id" :src="image.src">
</template>

<script>
import Button from './Button'

export default {
    name: "ChangeChart",
    components: {
        'v-btn' :  Button,
    },
    data(){
        // https://stackoverflow.com/questions/61728016/vue-js-change-image-src-with-a-click
        return{
            image: null,
            images: [{
                id: 1,
                src: "barchart-color.png", // https://www.reddit.com/r/vuejs/comments/a5m0xg/quick_question_using_vuecli_3_absolute_path_to/
                alt: "Een staafdiagram over kleuren"
            },
            {
                id: 2,
                src: "barchart-brand.png",
                alt: "Een staafdiagram over automerken"
            }
            ]
        }
    },
    mounted(){
        this.showOne(),
        this.showTwo()
    },
    methods: {
        showOne(){
            this.image = this.images[1];
        },
        showTwo(){
            this.image = this.images[0]
        }
    }
};
</script>

<style scoped>

    img{
        width: 100%;
    }

    div{
        display: flex;
        flex-direction: row;
    }
</style>