<script>
export default {
  props: {
    id: {
      type: String,
      default: '',
    },
    name: {
      type: String,
      default: '',
    },
  },
}
</script>

<template>
  <div>
    <input :id="id" type="checkbox" :name="name" />
    <label :for="id"><slot /></label>
  </div>
</template>

<style lang="scss" module>
@import '@design';
</style>
