<template>
  <span>
    <button @click="addLike">Добавить лайк</button>
    <div>{{ likes }}</div>
  </span>
  <span>
    <button @click="addDislike">Добавить дизлайк</button>
    <div>{{ dislikes }}</div>
  </span>
</template>

<script>
export default {
  data() {
    return {
      likes: 0,
      dislikes: 0,
    }
  },
  methods: {
    addLike() {
      this.likes += 1
    },
    addDislike() {
      this.dislikes += 1
    }
  }
}


</script>

<style>
</style>
