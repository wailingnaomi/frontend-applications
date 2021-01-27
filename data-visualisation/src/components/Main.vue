<template>
    <h1>Wat voor personenauto zien we het meest in Nederland?</h1>

    <section>
        <p>Nederland staat bekend om het fietsen, we worden wel eens het fietsland genoemd. Maar uit een <a href="https://www.cbs.nl/nl-nl/visualisaties/verkeer-en-vervoer/personen/mobiliteit" target="_blank">onderzoek van het CBS over mobiliteit van personen (2019)</a>, verplaatsen we toch net iets meer met de auto (46 procent) dan met de fiets (28 procent). In wat voor auto rijden we dan?</p>
    </section>
    <section>   
        <h3>In de grafiek hieronder kun je zien welke kleuren en automerken populair zijn onder personenauto’s in Nederland.</h3>
     
        <div>
            <v-btn v-if="image" :key="image.id" @click="showTwo" :src="image.src"  >Kleuren</v-btn>  
            <v-btn v-if="image" :key="image.id" @click="showOne" :src="image.src">Automerken </v-btn>
        </div>
        
        <img v-if="image" :key="image.id" :src="image.src">
    </section>
    

    <section>
        <p>We zien dat een <strong>grijze</strong> gekleurde auto een favoriet is bij personenauto’s en voor de automerken is dat de <strong>Toyota</strong>. Erg interessant, niet? De vraag is nu; is een grijze Toyota de auto die je het meest ziet in Nederland?</p>
    </section>
   
    <section>
        <!-- https://stackoverflow.com/questions/48847644/how-to-bind-img-src-to-data-in-vue -->
        <img v-bind:src="require('../../public/'+ images[2].src)">
    </section>
    
    <Conclusion />

</template>

<script>
import Button from './Button';
import Conclusion from './Conclusion'

export default {
    name: "Main",
    components: {
        'v-btn' : Button,
        Conclusion,
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
            },
            {
                id: 3,
                src: "stacked-barchart.png",
                alt: "Een gestapeld staafdiagram over automerken en kleuren"
            }
            ]
        }
    },
    mounted(){
        this.showOne(),
        this.showTwo()
    },
    methods: {
        // https://codeburst.io/creating-reusable-components-with-vue-js-button-component-503167facfde
        // consoleClick(){
        //     console.log('btn clicked')
        // },
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

    section{
        margin: 20em 0;
    }

    h1{
    font-size: 36px;
    margin: 8em 0;
    }

    h3{
        margin: 2em 0;
    }

    p{
        margin: 1em 0;
    }

    a{
        color: #000;
        text-decoration: none;
    }

    a:hover{
        color: #CCCCCC;
    }
    
    div{
        display: flex;
        flex-direction: row;
    }

    img{
        width: 100%;
    }

</style>