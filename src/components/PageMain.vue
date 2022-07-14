<template>
    <main>
        
        <section v-if="movieCards.length">

            <!--sezione cards films-->
            <h2>Film</h2>

            <ul>
                <!--singola card-->
                <CardComponent
                v-for="card in movieCards"
                :key="card.id"
                :item="card"/>
            </ul>

            <!--sezione cards serie-->
            <h2>Serie Tv</h2>

            <ul>
                <CardComponent 
                v-for="card in seriesCards"
                :key="card.id"
                :item="card"/> 
            </ul>

        </section>
    </main>
</template>

<script>
import CardComponent from './CardComponent.vue';

export default {
    name:'PageMain',
    props: {
        "movieCards": Array,
        "seriesCards": Array,
        "searching": Boolean
    },
    components: {
        CardComponent
    }
}
</script>

<style lang="scss" scoped>

main {
    background-color: grey;
}

ul {
    list-style-type: none;
    display: flex;
    flex-wrap: wrap;
}

</style>


