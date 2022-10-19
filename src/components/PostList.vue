<template>
  <h2 class="posts-title" v-if="posts.length">Список чего-то:</h2>
  <h2 class="posts-title" v-else style="color: red" >Список пуст</h2>
  <ul class="posts">
    <post-item
        class="post"
        :post="post"
        v-for="post in posts"
        :key="post.id"
        @remove="$emit('remove', post)"
    />
  </ul>
</template>

<script>
import PostItem from "@/components/PostItem";
export default {
  components: {PostItem},
  props: {
    posts: {
      type: Array,
      required: true,
    },
  }
}
</script>

<style>

.posts-title {
  align-self: flex-start;
}

.posts {
  list-style: none;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
  gap: 15px;
  width: 100%;
  height: 100%;
  margin-top: 15px;
}

</style>