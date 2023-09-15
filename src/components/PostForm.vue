<template>
  <form @submit.prevent>
    <label for="name">Add name</label>
    <input
        v-model="post.title"
        type="text"
        id="name"
        placeholder="name">
    <label for="description">Add Description</label>
    <input
        v-model="post.body"
        type="text"
        id="description"
        placeholder="description">
    <button class="btn"
            @click="createPost"
    >Create
    </button>
  </form>

</template>

<script>
export default {
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


input {
  width: 100%;
  border: 1px solid teal;
  padding: 10px 15px;
  margin-bottom: 20px;
}

.app {
  padding: 20%;
}

form {
  display: flex;
  flex-direction: column;
}

.btn {
  margin-top: 15px;
  align-self: flex-end;
  padding: 10px 15px;
  background: none;
  color: teal;
  border: 1px solid teal;
}

.btn:hover {
  background: teal;
  color: white;
}

label {
  font-size: 15px;
  margin-bottom: 5px;

}
</style>