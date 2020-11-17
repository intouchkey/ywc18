<template>
  <div class="restaurants-container">
    <div v-for="merchant in merchants" :key="merchant" :name="merchant">
      <RestaurantBox :merchant="merchant"></RestaurantBox>
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
}
</style>
