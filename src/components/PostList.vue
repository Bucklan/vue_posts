<template>
  <div>
    <h3>List users</h3>
    <post-item
        v-for="post in posts"
        v-bind:post="post"
    v-bind:key="post.id"
        @remove="$emit('remove',post)"
    />
  </div>
</template>

<script>
import PostItem from "@/components/PostItem.vue";

export default {
  components: {PostItem},
  props: {
    posts: {
      type: Array,
      required: true,
    }
  }
}
</script>

<style lang="scss" scoped>

</style>