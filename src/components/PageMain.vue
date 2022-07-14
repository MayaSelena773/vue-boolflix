<template>
    <main>
        <!--sezione cards films-->
        <section class="movie-cards" v-if="movieCards.length">

            <h1>Film</h1>

            <ul>
                <!--singola card-->
                <CardComponent
                v-for="card in movieCards"
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


