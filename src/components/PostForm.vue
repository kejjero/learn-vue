<template>
  <form action="" class="form" @submit.prevent="createPost">
    <input
        v-model="post.title"
        type="text"
        placeholder="Заголовок"
        class="input"
    >
    <input
        v-model="post.description"
        type="text"
        placeholder="Описание"
        class="input"
    >
    <button type="submit" class="btn">Добавить</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      post: {
        title: "",
        description: "",
      }
    }
  },

  methods: {
    createPost() {
      this.post.id = Date.now()
      this.$emit("create", this.post)
      this.post = {
        title: "",
        description: ""
      }
    }
  }
}
</script>

<style>

</style>