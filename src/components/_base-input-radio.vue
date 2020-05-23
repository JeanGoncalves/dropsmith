<script>
export default {
  inheritAttrs: false,
  props: {
    name: {
      type: String,
      required: true,
    },
    labels: {
      type: Array,
      required: true,
      default: () => [],
    },
  },
  data() {
    return {
      picked: '',
    }
  },
}
</script>

<template>
  <div>
    <label v-for="label in labels" :key="label.value" :class="$style.container">
      {{ label.title }}
      <input
        :id="label.id"
        v-model="picked"
        type="radio"
        :name="name"
        :class="$style.radio"
        :value="label.value"
        :click="$emit('callback', picked)"
      />
      <span :class="$style.checkmark"></span>

      <span :class="$style.subtitle">{{ label.subtitle }}</span>
      <sub :class="$style.detail">{{ label.detail }}</sub>
    </label>
  </div>
</template>

<style lang="scss" module>
@import '@design';

/* Create a custom radio button */
.checkmark {
  position: absolute;
  top: 0;
  left: 0;
  width: 21px;
  height: 21px;
  background-color: #eee;
  border-radius: 50%;

  ::after {
    position: absolute;
    display: none;
    content: '';
  }
}
.container {
  position: relative;
  display: flex;
  justify-content: space-between;
  padding-left: 35px;
  margin-bottom: 12px;
  cursor: pointer;
  user-select: none;

  .radio {
    position: absolute;
    cursor: pointer;
    opacity: 0;

    :checked ~ .checkmark {
      background-color: #89c157;

      ::after {
        display: block;
      }
    }
  }

  :hover .radio ~ .checkmark {
    background-color: #ccc;
  }

  .checkmark::after {
    top: 6px;
    left: 6px;
    width: 9px;
    height: 9px;
    background: white;
    border-radius: 50%;
  }
}

.subtitle {
  font-weight: bold;
}

.detail {
  position: absolute;
  bottom: -10px;
  color: #89c157;
}
</style>
