<template>
  <div class="py-0 px-0">
    <Navbar :override-show="true" />
    <div class="container">
      <div class="columns is-multiline">
        <div class="column is-6">
          <!-- <picture class="image"
            ><source
              :srcset="product.media.source"
              media="(max-width: 1023px)" />
            <source
              :srcset="product.media.source"
              media="(min-width: 1024px)" />
            <img
              :src="product.media.source"
              width="216"
              height="326"
              alt="Cotton Sweater"
              style=""
          /></picture> -->
        </div>
        <div class="column is-6 py-6 px-6">
          <!-- <p class="title is-4">{{ product.name }}</p> -->
          <!-- eslint-disable-next-line -->
          <!-- <p v-html="product.description"></p> -->
          <!-- <h1>{{ category.name }}</h1> -->

          <!-- {{ categories }}
            {{ slug }} -->
          <!-- <product-list :products="products"></product-list> -->

          <div v-for="prod in products" :key="prod.name">
            {{ prod.name }}
          </div>

          <pre>
           {{ products }}
         </pre
          >

          <!-- {{ product.name }} -->

          <!-- <Stars :rating="4" /> -->
          <!-- <p><AddToCartBtn :product="product" /></p> -->
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  //   async asyncData({ $commerce }) {
  //     const categorySlug = "bellen"
  //     const category = await $commerce.categories.retrieve(categorySlug, {
  //       type: "slug",
  //     })
  //     return {
  //       category,
  //     }
  //   },
  // }

  async asyncData({ params, $commerce }) {
    const categorySlug = params.slug
    console.log(categorySlug)
    // const { slug } = params
    const { data: products } = await $commerce.products.list({
      // type: "slug",
      category_slug: categorySlug,
    })
    return { products }
  },
}
</script>

<style lang="scss" scoped>
.container {
  padding-top: 8rem;
  padding-bottom: 4rem;
}

@include mobile {
  padding-top: 10rem;
}
</style>
