<template>
  <div class="dialog" v-if="show" @click="hiddenDialog">
    <div @click.stop class="dialog__content">
      <slot></slot>
    </div>
  </div>
</template>

<script>
import PostForm from "@/App";
export default {
  components: {PostForm},
  name: 'my-dialog',
  props: {
    show: {
      type: Boolean,
      default: false
    }
  },
  methods: {
    hiddenDialog() {
      this.$emit("update:show", false)
    },
  }
}
</script>

<style scoped>
.dialog {
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  position: fixed;
  background-color: rgba(0, 0, 0, 0.6);
  display: flex;
  z-index: 1000;
}

.dialog__content {
  background-color: #fff;
  min-width: 500px;
  margin: auto;
  padding: 20px;
}
</style>