<template>
  <b-container class="restaurant-container">
    <div
      class="main"
      style="width: 100%; display: inline-flex; justify-content: space-between"
    >
      <div class="no-pm" style="display: flex">
        <b-img
          class="img-fluid cover-image"
          :src="merchant.coverImageId"
          alt="Image"
        ></b-img>
      </div>
      <RestaurantInfoBox :merchant="merchant"></RestaurantInfoBox>
    </div>
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
  padding: 5px 5px 0px 5px;
  border: 1px solid #dae9f0;
  background-color: white;
  margin-bottom: 10px;
}
.cover-image {
  width: 250px;
  height: 250px;
}
.no-pm {
  width: 35%;
  padding: 0;
  margin: 0;
}

@media screen and (max-width: 576px) {
  .main {
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
  .restaurant-container {
    padding: 0px;
  }
  .cover-image {
    width: 100%;
    height: 250px;
  }
  .no-pm {
    width: 100%;
  }
}
</style>
