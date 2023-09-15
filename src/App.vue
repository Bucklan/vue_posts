<template>


  <div class="app">
    <div>
      <form>
        <label for="name">Add name</label>
        <input type="text" id="name" placeholder="name">
        <label for="description">Add Description</label>
        <input type="text" id="description" placeholder="description">
        <button class="btn" @click="createPost">Create </button>
      </form>
    </div>
    <div class="post" v-for="post in posts">
      <div><strong>Name: </strong> {{ post.title }}</div>
      <div><strong>Description: </strong> {{ post.body }}</div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      posts: [
        {id: 1, title: 'JavaScript', body: 'Description posts'},
        {id: 2, title: 'JavaScript 2', body: 'Description posts 2'},
        {id: 3, title: 'JavaScript 3', body: 'Description posts 3'},
      ]
    }
  },
  methods
}

</script>
<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.post {
  padding: 1rem;
  border: 3px solid teal;
  margin: 20px;
}
input{
  width: 100%;
  border: 1px solid teal;
  padding: 10px 15px;
  margin-bottom: 20px;
}
.app{
  padding: 20%;
}
form{
  display: flex;
  flex-direction: column;
}
.btn{
  margin-top: 15px;
  align-self: flex-end;
  padding: 10px 15px;
  background: none;
  color: teal;
  border: 1px solid teal;
}
.btn:hover{
  background: teal;
  color: white;
}
label{
  font-size: 15px;
  margin-bottom: 5px;

}
</style>