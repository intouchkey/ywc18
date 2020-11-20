<template>
  <div class="open-status-container">
    <div class="box open-color" v-if="isOpen == 'Y'">เปิดอยู่</div>
    <div class="box close-color" v-else>ปิดแล้ว</div>
  </div>
</template>

<script>
export default {
  name: 'OpenStatusBox',
  props: ['isOpen'],
}
</script>

<style>
.open-status-container {
  display: inline-flex;
  margin-left: 10px;
}
.box {
  display: flex;
  color: white;
  padding: 3px 10px 3px 10px;
  border-radius: 3px;
  font-size: 15px;
}
.open-color {
  background-color: #36c624;
}
.close-color {
  background-color: #a1a1a1;
}
</style>
