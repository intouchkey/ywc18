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
      :selected="provinceSelected"
      @update-selected="updateProvinceSelected"
    ></CustomDropDown>

    <CustomDropDown
      :items="priceRange"
      topic="ราคา"
      defaultText="กรุณาเลือก"
      :selected="priceSelected"
      @update-selected="updatePriceSelected"
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
  props: [
    'categories',
    'subcategories',
    'priceRange',
    'provinces',
    'selectedSearchText',
    'provinceSelected',
    'priceSelected'
  ],
  data() {
    return {
      categorySelected: 'ทั้งหมด',
      subcategorySelected: '',
    }
  },
  methods: {
    updateSubcategorySelected(selected) {
      this.subcategorySelected = selected
      this.$emit(
        'update-search-text',
        this.categorySelected == 'ทั้งหมด'
          ? 'ทั้งหมด'
          : this.categorySelected + " " + this.subcategorySelected
      )
    },
    updateCategorySelected(selected) {
      this.categorySelected = selected
      this.$emit(
        'update-search-text',
        this.categorySelected
      )
    },
    updateProvinceSelected(selected) {
      this.$emit('update-province-selected', selected)
    },
    updatePriceSelected(selected) {
      this.$emit('update-price-selected', selected)
    }
  },
}
</script>

<style>
.filter-container {
  border: 1px solid #a1afc0;
  padding: 15px;
  line-height: 30px;
  background-color: white;
}
.topic {
  font-weight: bolder;
  color: black;
}
</style>
