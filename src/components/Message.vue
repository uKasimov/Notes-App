<template>
  <p class="message">{{ message }}</p>
</template>

<script>
export default {
  props: {
    message: {
      type: String,
      // required: true
      default: 'default message'
    }
  }
}
</script>

<style lang="scss" scoped>
.message {
  color: #b53f3f;
  text-align: center;
  padding: 20px;
}
</style>