<template>
  <div class="content">
    <post-form @create="createPost"/>
    <post-list :posts="posts"/>
  </div>
</template>

<script>
import PostList from "@/components/PostList";
import PostForm from "@/components/PostForm";
export default {
  components: {PostList, PostForm},
  data() {
    return {
      posts: [
        {id: 1, title: "JavaScript 1", description: "Информация о JavaScript 1"},
        {id: 2, title: "JavaScript 2", description: "Информация о JavaScript 2"},
        {id: 3, title: "JavaScript 3", description: "Информация о JavaScript 3"},
      ],
    }
  },
  methods: {
    createPost(post) {
      this.posts.push(post)
    }
  }
}


</script>

<style>

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.content {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  max-width: 800px;
  margin: 0 auto;
}

.form {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  gap: 15px;
  margin-top: 110px;
}

.input {
  margin: 0;
  padding: 10px 5px;
  width: 100%;
}

.btn {
  margin: 0;
  padding: 10px 15px;
  background-color: black;
  color: #fff;
  border: none;
  font-size: 14px;
  align-self: flex-end;
}


</style>
