<template>
    <main>
        <section class="movie-cards" v-if="movieCards.length">
            <h1>Film</h1>

            <ul class="cards">

                <CardComponent
                v-for="card in movieCards"
                :key="card.id"
                :item="card"/>

            </ul>

        </section>
    </main>
</template>

<script>
import CardComponent from './/CardComponent.vue';

export default {
    name:'PageMain',
    props: {
        "movieCards": Array,
        "searching": Boolean
    }
}
</script>

<style lang="scss" scoped>

</style>


