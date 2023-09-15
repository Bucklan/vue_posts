<template>
  <div class="app">
    <post-form
        @create="createPost"
    />
    <post-list v-bind:posts="posts"
    />
  </div>
</template>
<script>
import PostForm from "@/components/PostForm.vue";
import PostList from "@/components/PostList.vue";

export default {
  components: {
    PostList, PostForm
  },
  data() {
    return {
      posts: [
        {id: 1, title: 'JavaScript', body: 'Description posts'},
        {id: 2, title: 'JavaScript 2', body: 'Description posts 2'},
        {id: 3, title: 'JavaScript 3', body: 'Description posts 3'},
      ],
    }
  },
  methods: {
    createPost(post) {
      this.posts.push(post)
    },
    removePost(post) {
      this.posts = this.posts.filter(p => p.id !== post.id)
    }
  }
}

</script>
<style>
</style>