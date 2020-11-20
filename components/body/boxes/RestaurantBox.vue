<template>
  <b-container class="restaurant-container">
    <b-row class="h-80">
      <b-col cols="3" class="no-pm">
        <b-img
          class="img-fluid cover-image"
          :src="merchant.coverImageId"
          alt="Image"
        ></b-img>
      </b-col>
      <b-col cols="9" class="restaurant-info-container">
        <p class="shop-bold">{{ merchant.shopNameTH }}</p>
        <p class="shop-grey" v-html="merchant.fullDescription"></p>
        <hr class="solid" />
        <p class="shop-grey" v-html="merchant.highlightText"></p>
        <strong class="menu-suggested">เมนูแนะนำ:</strong>
        <p class="shop-grey inline">
          {{ merchant.recommendedItems.join(',') }}
        </p>
        <FacilitiesSection
          :facilities="merchant.facilities"
        ></FacilitiesSection>
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
  padding: 5px;
  border: 1px solid #dae9f0;
  margin-bottom: 10px;
}
.restaurant-info-container {
  margin-top: 10px;
}
.no-pm {
  padding: 0;
  margin: 0;
}
.cover-image {
}
.shop-bold {
  font-size: 20px;
  font-weight: bold;
}
.shop-grey {
  font-size: 17px;
  color: grey;
}
.inline {
  display: inline;
}
.black {
  color: black;
}
</style>
