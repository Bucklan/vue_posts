<template>
  <input type="text" class="input" v-bind:value="modelValue" @input="updateInput">
</template>

<script>
export default {
  name: 'my-input',
  props:{
    modelValue: [String,Number]
  },
  methods : {
    updateInput(event){
      this.$emit('update:modelValue',event.target.value)
    }
  }
}
</script>

<style lang="scss" scoped>
input {
  width: 100%;
  border: 1px solid teal;
  padding: 10px 15px;
  margin-bottom: 20px;
}
</style>