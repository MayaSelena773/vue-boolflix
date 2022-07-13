<template>
<header>
    <div>BOOLFLIX</div>

    <div>
        <input placeholder="scrivi un titolo"></input>
        <button type="primary">cerca</button>
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
    background-color: lightblue;
    display: flex;
    justify-content: space-between;
    height: 20px;
}

</style>


