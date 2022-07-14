<template>
<header>
    <!--Logo header-->
    <div class="logo">BOOLFLIX</div>
    <!--input search film-->
    <div>
        <input 
        v-model="movieTitle" 
        type="text"
        placeholder="scrivi un titolo"
        @keyup.enter="$emit('searchTitle', movieTitle)">
        
        <button class="my_btn" @click="$emit('searchTitle', movieTitle)">cerca</button>
    </div>

</header>
</template>

<script>
export default {
    name:'PageHeader',
    data(){
        return{
            movieTitle: ''
        }
    }
}
</script>

<style lang="scss" scoped>

header {
    background-color: black;
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 100px;
    padding-left: 20px;
    padding-right: 20px;

    .logo {
        color: red;
    }

    input {
        padding: 7px;
    }

    .my_btn {
        padding: 7px;
        border: 1px solid white;
        background-color: lightcoral;
    }
}

</style>


