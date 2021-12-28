<template>
  <div>
    <Navbar :override-show="true" />
    <div class="container">
      <div class="section">
        <h1 class="title">Cats</h1>
        <category-list :categories="categories"></category-list>

        <pre>
          {{ categories }}
        </pre>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  async asyncData({ $commerce }) {
    // data() {
    //   return {
    //     categorie: {}
    //   }
    // },
    //    props: {
    //   category: { type: Object, defaultValue: {}, required: true },
    // },
    const { data: categories } = await $commerce.categories.list()
    return {
      categories,
    }
  },
}
</script>

<style lang="scss" scoped>
.container {
  padding-top: 8rem;
  padding-bottom: 4rem;
}
</style>
