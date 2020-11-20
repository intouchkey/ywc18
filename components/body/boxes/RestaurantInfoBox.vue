<template>
  <div class="restaurant-info-container">
    <div style="display: inline-flex; align-items: baseline">
      <p class="shop-bold">{{ merchant.shopNameTH }}</p>
      <OpenStatusBox :isOpen="merchant.isOpen"></OpenStatusBox>
    </div>
    <p class="shop-grey" v-html="merchant.fullDescription"></p>
    <div class="copy-hr"></div>
    <p class="shop-grey" v-html="merchant.highlightText"></p>
    <div style="display: inline-flex">
      <strong class="menu-suggested">เมนูแนะนำ:</strong>
      <p class="shop-grey recommend-items">
        {{ merchant.recommendedItems.join(', ') }}
      </p>
    </div>
    <FacilitiesSection :facilities="merchant.facilities"></FacilitiesSection>
  </div>
</template>

<script>
export default {
  name: 'RestaurantInfoBox',
  props: ['merchant'],
}
</script>

<style>
.restaurant-info-container {
  width: 100%;
  margin-top: 10px;
  display: flex;
  flex-direction: column;
  margin-left: 10px;
}
.copy-hr {
  width: 65%;
  height: 1.2px;
  margin-top: 10px;
  margin-bottom: 20px;
  background-color: #c4c4c4;
}
.shop-bold {
  font-size: 20px;
  font-weight: bold;
  margin-bottom: 8px;
  display: flex;
}
.shop-grey {
  font-size: 14px;
  color: grey;
  margin-bottom: 8px;
}
.recommend-items {
  font-size: 14px;
  display: flex;
}
.menu-suggested {
  font-size: 14px;
  display: flex;
  padding-right: 5px;
}
.black {
  color: black;
}

@media screen and (max-width: 576px) {
  .restaurant-info-container {
    width: 100%;
    padding: 10px;
    margin-left: 0px;
  }
  .copy-hr {
    width: 60%;
  }
}
</style>
