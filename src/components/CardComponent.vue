<template>
    <section>
        <li>
            <span>Titolo:{{item.title}}</span>
            <span>Titolo originale:{{item.original_title}}</span>
            <span>Lingua:{{item.original_language}}</span>
            <span>Voto:{{item.vote_average}}</span>
        </li>
    </section>
</template>

<script>
export default {
    name:'CardComponent',
    data: function() {
        return {

        }
    },
    props: {
        "item": Object
    }
}
</script>

<style lang="scss" scoped>

li {
    background-color: white;
    padding: 10px;
    margin: 5px;
}

</style>


