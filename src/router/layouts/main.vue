<script>
import NavBar from '@components/nav-bar.vue'

export default {
  components: { NavBar },
  props: {
    hasNavbar: {
      type: String,
      default: 'true',
    },
  },
}
</script>

<template>
  <div :class="$style.container">
    <NavBar v-if="hasNavbar" />
    <slot />
  </div>
</template>

<style lang="scss" module>
@import '@design';

.container {
  min-width: $size-content-width-min;
  max-width: $size-content-width-max;
  margin: 0 auto;
}
</style>
