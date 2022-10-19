<template>
  <div class="content">
    <my-dialog v-model:show="dialogVisible" >
      <post-form @create="createPost"/>
    </my-dialog>
    <h1>Главная страница</h1>
    <my-button @click="setDialogVisible">Добавить пост</my-button>
    <post-list :posts="posts" @remove="removePost"/>
  </div>
</template>

<script>
import axios from "axios"
import PostList from "@/components/PostList";
import PostForm from "@/components/PostForm";
import MyDialog from "@/components/UI/MyDialog";
import MyButton from "@/components/UI/MyButton";
export default {
  components: {MyButton, MyDialog, PostList, PostForm},
  data() {
    return {
      posts: [],
      dialogVisible: false,
    }
  },
  methods: {
    createPost(post) {
      this.posts.push(post)
      this.dialogVisible = false;

    },
    removePost(post) {
      this.posts = this.posts.filter(item => item.id !== post.id)
    },
    setDialogVisible() {
      this.dialogVisible = true
    },
    async getPosts () {
      try {
        const response = await axios.get("https://jsonplaceholder.typicode.com/posts?_limit=10")
        this.posts = response.data
      } catch (err) {
        alert("Ошибка " + err)
      }
    },
  },
  mounted() {
    this.getPosts()
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


</style>
