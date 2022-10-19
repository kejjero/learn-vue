<template>
  <button type="submit" class="btn">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: "my-button"
}
</script>

<style>
.btn {
  margin: 0;
  padding: 10px 15px;
  background-color: black;
  color: #fff;
  border: none;
  font-size: 14px;
  align-self: flex-end;
  cursor: pointer;
  transition: transform ease-in-out 0.2s;
  transform: scale(1);
}

.btn:hover {
  transform: scale(1.05);
}

</style>