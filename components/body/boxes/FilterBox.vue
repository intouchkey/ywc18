<template>
  <div class="filter-container">
    <CustomFormRadio
      topic="ประเภทร้านค้า"
      :items="categories"
      :selected="categorySelected"
      @update-selected="updateCategorySelected"
    ></CustomFormRadio>
    <CustomDropDown
      :items="provinces"
      topic="จังหวัด/ใกล้ฉัน"
      defaultText="พื้นที่ไกล้ฉัน"
    ></CustomDropDown>
    <CustomDropDown
      :items="priceRange"
      topic="ราคา"
      defaultText="กรุณาเลือก"
    ></CustomDropDown>
    <div v-if="categorySelected && categorySelected != 'ทั้งหมด'">
      <CustomFormRadio
        topic="ประเภทร้านอาหารและเครื่องดื่ม"
        :items="subcategories[categorySelected]"
        :selected="subcategorySelected"
        @update-selected="updateSubcategorySelected"
      ></CustomFormRadio>
    </div>
  </div>
</template>

<script>
export default {
  name: 'FilterBox',
  props: ['categories', 'subcategories', 'priceRange', 'provinces'],
  data() {
    return {
      categorySelected: '',
      subcategorySelected: '',
    }
  },
  methods: {
    updateSubcategorySelected(selected) {
      this.subcategorySelected = selected
    },
    updateCategorySelected(selected) {
      this.categorySelected = selected
    },
  },
}
</script>

<style>
.filter-container {
  border: 1px solid black;
  padding: 15px;
}
.topic {
  font-weight: bolder;
}
</style>
