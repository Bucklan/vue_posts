<template>
  <form @submit.prevent>
    <label for="name">Add name</label>
    <my-input
        v-model="post.title"
        type="text"
        id="name"
        placeholder="name"/>
    <label for="description">Add Description</label>
    <my-input
        v-model="post.body"
        type="text"
        id="description"
        placeholder="description"/>
    <my-button
        class="btn"
        @click="createPost">Create
    </my-button>
  </form>

</template>

<script>

import MyInput from "@/components/UI/MyInput.vue";
import MyButton from "@/components/UI/MyButton.vue";

export default {
  components: {MyButton, MyInput},
  data() {
    return {
      post: {
        title: '',
        body: '',
      }
    }
  },
  methods: {
    createPost() {
      this.post.id = Date.now();
      this.$emit('create',this.post)
      this.post = {
        title: '',
        body: '',
      }
    },
  }
}
</script>

<style lang="scss" scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}




.app {
  padding: 20%;
}

form {
  display: flex;
  flex-direction: column;
}


label {
  font-size: 15px;
  margin-bottom: 5px;

}
</style>