<template>
  <div>
    <div class="post" v-for="post in posts">
      <div><strong>Name: </strong> {{ post.title }}</div>
      <div><strong>Description: </strong> {{ post.body }}</div>
    </div>
  </div>
</template>

<script>
export default {
props: {
  posts: {
    type : Array,
    required: true,
  }
}
}
</script>

<style lang="scss" scoped>
.post {
  padding: 1rem;
  border: 3px solid teal;
  margin: 20px;
}
</style>