<template>
    <section>
        <!--Componenti della card-->
        <li>
            <!--Titoli sia per film che per serie-->
            <div>Titolo:{{item.title ? item.title : item.name}}</div>
            <div>Titolo originale:{{item.original_title ? item.original_title : item.original_name}}</div>

            <!--Immagini per film, serie e di default (se non c'è nessuna immagine)-->
            <div>
                <img v-if="item.poster_path" class="poster" :src="`https://image.tmdb.org/t/p/w342${item.poster_path}`" alt="poster">
                <img v-else class="poster" src="../assets/img/default-img.gif" alt="poster_default">
            </div>

            <!--Lingua originale con bandiera per ita o ing-->
            <div>Lingua:
                <img 
                v-if="availableflags.includes(item.original_language)" 
                :src="require(`../assets/img/${item.original_language}.png`)" 
                :alt="item.original_language">
                <span v-else>{{item.original_language}}</span>
            </div>
            
            <!--Voto film-->
            <div>Voto:{{item.vote_average}}</div>
            <div>Voto Arrotondato:{{getStars(item.vote_average)}}
                <i v-for="n in getStars(item.vote_average)" :key="n" class="fas fa-star"></i>
                <i v-for="n in 5 - getStars(item.vote_average)" :key="n" class="far fa-star"></i>
            </div>
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
    methods: {
        getStars(original_vote){
            //Arrotondare il voto per eccesso
            //Poi dividerlo per due (per passare al voto con 5 stelle di range)
            return Math.round(original_vote / 2);
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
        padding: 5px;
    }

    .poster {
        width: 150px;
    }
}
</style>


