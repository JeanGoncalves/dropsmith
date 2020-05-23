<script>
import Layout from '@layouts/main.vue'

export default {
  page: {
    title: 'Checkout',
    meta: [{ name: 'description', content: 'The Checkout page.' }],
  },
  components: { Layout },
}
</script>

<template>
  <Layout :has-navbar="false">
    Checkout View
  </Layout>
</template>

<style lang="scss" module>
@import '@design';
</style>
