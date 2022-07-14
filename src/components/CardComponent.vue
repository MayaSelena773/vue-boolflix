<template>
    <section>

        <li>
            <div>Titolo:{{item.title ? item.title : item.name}}</div>
            <div>Titolo originale:{{item.original_title ? item.original_title : item.original_name}}</div>
            <div>Lingua:
                <img 
                v-if="availableflags.includes(item.original_language)" 
                :src="require(`../assets/img/${item.original_language}.png`)" 
                :alt="item.original_language">
                <span v-else>{{item.original_language}}</span>
            </div>
            <div>Voto:{{item.vote_average}}</div>
        </li>

    </section>
</template>

<script>


export default {
    name:'CardComponent',
    data() {
        return {
            availableflags: ['it', 'en']

        };
    },
    props: {
        "item": Object
    }
}
</script>

<style lang="scss" scoped>

li {
    background-color: white;
    width: 300px;
    height: 420px;
    padding: 10px;
    margin: 5px;
    display: flex;
    flex-direction: column;

    img {
        width: 30px;
    }

    div {
        padding: 10px;
    }
}
</style>


