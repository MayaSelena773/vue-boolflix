<template>
<header>
    <div class="logo">BOOLFLIX</div>

    <div>
        <input placeholder="scrivi un titolo">
        <button class="my_btn">cerca</button>
    </div>

</header>
</template>

<script>
export default {
    name:'PageHeader'
}
</script>

<style lang="scss" scoped>

header {
    background-color: black;
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 50px;
    padding-left: 20px;
    padding-right: 20px;

    .logo {
        color: red;
    }

    input {
        padding: 8px;
    }

    .my_btn {
        padding: 8px;
        border: 1px solid white;
        background-color: lightcoral;
    }
}

</style>


