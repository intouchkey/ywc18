<template>
  <b-container class="restaurant-container">
    <b-row>
      <b-col cols="4">
        <b-img
          class="cover-image"
          :src="merchant.coverImageId"
          alt="Image"
        ></b-img>
      </b-col>
      <b-col cols="8">
        <p class="shop-name">{{ merchant.shopNameTH }}</p>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
export default {
  name: 'RestaurantBox',
  props: ['merchant'],
}
</script>

<style>
.restaurant-container {
  padding: 0;
  border: 1px solid black;
  margin-bottom: 10px;
}
.row,
.col {
  padding: 0;
  margin: 0;
}
.cover-image {
  width: 300px;
  height: 300px;
  object-fit: cover;
}
.shop-name {
  font-size: 20px;
  font-weight: bold;
}
</style>
