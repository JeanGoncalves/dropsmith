<script>
export default {
  props: {
    title: {
      type: String,
      default: '',
    },
    description: {
      type: String,
      default: '',
    },
    info: {
      type: String,
      default: '',
    },
  },
}
</script>

<template>
  <div :class="$style.cardInfo">
    <div :class="$style.title">{{ title }}</div>
    <div :class="$style.description">{{ description }}</div>
    <div :class="$style.info">{{ info }}</div>
  </div>
</template>

<style lang="scss" module>
@import '@design';

.cardInfo {
  padding: 18px;
  text-align: center;
  border: 2px solid #e6e6e6;
}
</style>
