<template>
  <div class="posts">
    <div><strong>Name: </strong> {{ post.title }}</div>
    <div><strong>Description: </strong> {{ post.body }}</div>
      <my-button @click="$emit('remove',post)">Delete</my-button>
  </div>
</template>
<script>

import MyButton from "@/components/UI/MyButton.vue";

export default {
  components: {MyButton},
  props: {
    post: {
      type: Object,
      required: true,
    }
  }
}
</script>

<style lang="scss" scoped>
.posts {
  padding: 1rem;
  border: 3px solid teal;
  margin: 20px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>