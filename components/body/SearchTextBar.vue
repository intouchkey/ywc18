<template>
  <p class="search-text">ผลการค้นหา {{ selectedText }}</p>
</template>

<script>
export default {
  name: 'SearchTextBar',
  props: ['selectedText'],
}
</script>

<style>
.search-text {
  color: black;
  font-size: 20px;
  font-weight: bold;
  margin-bottom: 50px;
}
</style>
