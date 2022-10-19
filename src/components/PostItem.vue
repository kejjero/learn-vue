<template>
  <li class="post">
    <div class="post__wrapper">
      <h3>{{ post.title }}</h3>
      <p>{{ post.body }}</p>
    </div>
<!--  emit поднимает событие в PostList с именем remove -->
    <my-button @click="$emit('remove', post)">Удалить</my-button>
  </li>
</template>

<script>
import MyButton from "@/components/UI/MyButton";
export default {
  components: {MyButton},
  props: {
    post: {
      type: Object,
      required: true,
    }
  }
}
</script>

<style>
.post {
  display: flex;
  justify-content: space-between;
  border: 2px solid #000;
  padding: 15px 10px;
  width: 100%;
}

.post__wrapper {
  display: flex;
  flex-direction: column;
  gap: 5px;
}
</style>