<template>
  <div class="body-container">
    <div class="row">
      <div class="col-12">
        <SearchTextBar></SearchTextBar>
      </div>
    </div>
    <div class="row">
      <div class="d-none d-sm-block col-sm-3">
        <FilterBox
          :categories="categories"
          :subcategories="subcategories"
          :priceRange="priceRange"
          :provinces="provinces"
        ></FilterBox>
      </div>
      <div class="col-sm-9 col-xs-12">
        <RestaurantBoxList :merchants="merchants"></RestaurantBoxList>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Body',

  props: [
    'categories',
    'subcategories',
    'priceRange',
    'provinces',
    'merchants',
  ],
}
</script>

<style>
.body-container {
  margin: 20px 10px;
}
</style>
