<template>
  <div>
    <p>{{ category.name }}</p>
    <p>{{ category.description }}</p>
  </div>
</template>

<script>
export default {
  props: {
    category: { type: Object, defaultValue: {}, required: true },
  },
}
</script>

<style lang="scss" scoped></style>
