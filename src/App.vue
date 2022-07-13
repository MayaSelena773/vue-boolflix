<template>
  <div id="app">
    <PageHeader />
  </div>
</template>

<script>
import PageHeader from './components/PageHeader.vue'

export default {
  name: 'App',
  components: {
    PageHeader
  }
}
</script>

<style lang="scss">
@import './components/style/common.scss';
</style>
