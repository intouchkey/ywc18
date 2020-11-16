<template>
  <div class="body-container">
   <div class="row"> <div class="col-12"><SearchTextBar></SearchTextBar></div></div>
    <div class="row">
        <div class="d-none d-sm-block col-lg-3 col-md-3 col-sm-3">
        <FilterBox></FilterBox>
        </div>
        <div class="col-lg-9 col-md-9 col-sm-9 col-xs-12">
        <RestaurantBox></RestaurantBox>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Body",
};
</script>

<style>
.body-container {
    margin: 20px 10px;
}
</style>
