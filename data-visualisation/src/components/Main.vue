<template>
    <h1>Wat voor personenauto zien we het meest in Nederland?</h1>

    <Introduction />

    <section>   
        <chart-title>In de grafiek hieronder kun je zien welke kleuren en automerken populair zijn onder personenauto’s in Nederland.</chart-title>
        <ChangeChart />
    </section>
    

    <section>
        <p>We zien dat een <strong>grijze</strong> gekleurde auto een favoriet is bij personenauto’s en voor de automerken is dat de <strong>volkswagen</strong>. Erg interessant, niet? De vraag is nu; is een grijze volkswagen de auto die je het meest ziet in Nederland?</p>
    </section>
   
   <section>
        <chart-title>Bekijk hier per automerk hoe de kleuren zijn verdeeld</chart-title>
        <StackedBarchart />
   </section>
    
    <Conclusion />

</template>

<script>
import Introduction from './Introduction';
import ChartTitle from './ChartTitle';
import ChangeChart from './ChangeChart';
import StackedBarchart from './StackedBarchart';
import Conclusion from './Conclusion';

export default {
    name: "Main",
    components: {
        Introduction,
        'chart-title' : ChartTitle,
        ChangeChart,
        StackedBarchart,
        Conclusion,
    },
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
</style>