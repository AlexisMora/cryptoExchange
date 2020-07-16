<template>
  <button
    @click="buttonClick"
    class="bg-transparent hover:bg-green-500 text-green-700 font-semibold hover:text-white py-2 px-4 border border-green-500 hover:border-transparent rounded"
  >
    <beat-loader :loading="isLoading" :color="'#68dc91'" :size="8" />
    <p v-show="!isLoading">
      <slot></slot>
    </p>
  </button>
</template>
<script>
export default {
  name: 'CxButton',
  props: {
    isLoading: {
      type: Boolean,
      default: false
    }
  },
  methods: {
    buttonClick() {
      this.$emit('custom-click')
    }
  }
}
</script>
