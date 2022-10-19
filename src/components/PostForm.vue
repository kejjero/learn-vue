<template>
  <form action="" class="form" @submit.prevent="createPost">
    <my-input
        v-model:value="post.title"
        type="text"
        placeholder="Заголовок"
        class="input"
    />
    <my-input
        v-model:value="post.body"
        type="text"
        placeholder="Описание"
        class="input"
    />
    <my-button>Добавить</my-button>
  </form>
</template>

<script>
export default {
  components: {},

  data() {
    return {
      post: {
        title: "",
        body: "",
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
.form {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  gap: 15px;
}
</style>