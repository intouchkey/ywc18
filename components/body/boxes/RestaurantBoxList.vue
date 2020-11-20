<template>
  <div class="restaurants-container">
    <div v-for="merchant in merchants" :key="merchant" :name="merchant">
      <RestaurantBox :merchant="merchant"></RestaurantBox>
    </div>
    <div class="button-wrapper">
      <button class="button">ดูเพิ่มเติม</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'RestaurantBoxList',
  props: ['merchants'],
}
</script>

<style>
.restaurants-container {
  margin-bottom: 20px;
}
.button-wrapper {
  margin-top: 40px;
  text-align: center;
}
button {
  width: 30%;
  padding: 10px;
  border: none;
  background: white;
  font-size: 15px;
}
button:focus {
  outline: 0;
}

@media screen and (max-width: 576px) {
  button {
    width: 50%;
  }
}
</style>
