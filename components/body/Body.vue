<template>
  <div class="body-container">
    <div class="row">
      <div class="col-12">
        <SearchTextBar :selectedText="selectedSearchText"></SearchTextBar>
      </div>
    </div>
    <div class="row">
      <div class="d-none d-sm-block col-sm-3">
        <FilterBox
          :categories="categories"
          :subcategories="subcategories"
          :priceRange="priceRange"
          :provinces="provinces"
          :selectedSearchText="selectedSearchText"
          :provinceSelected="provinceSelected"
          :priceSelected="priceSelected"
          @update-search-text="updateSearchText"
          @update-province-selected="updateProvinceSelected"
          @update-price-selected="updatePriceSelected"
        ></FilterBox>
      </div>
      <div class="col-sm-9 col-xs-12">
        <RestaurantBoxList :merchants="selectedMerchants"></RestaurantBoxList>
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

  data() {
    return {
      selectedSearchText: 'ทั้งหมด',
      selectedMerchants: this.merchants,
      provinceSelected: '',
      priceSelected: ''
    }
  },

  methods: {
    updateSearchText(searchText) {
      this.selectedSearchText = searchText

      const selected = searchText.split(' ')

      this.selectedMerchants = this.merchants.filter((selectMerchant) => {
        if (selected[0] && selected[0].includes('ทั้งหมด')) {
          return true
        }

        if (selected[0] == 'สินค้าทั่วไป') {
          return (
            selectMerchant.categoryName.includes('แฟชั่น') ||
            selectMerchant.categoryName.includes('งานบริการอื่นๆ / เบ็ดเตล็ด')
          )
        }

        return selected[0].includes(selectMerchant.categoryName)
      })

      if (selected[1]) {
        if (selected[1].includes('ทั้งหมด')) {
          return true
        }

        this.selectedMerchants = this.selectedMerchants.filter((s) => {
          return s.subcategoryName.includes(selected[1])
        })
      }

      if (this.provinceSelected != "พื้นที่ไกล้ฉัน" && this.provinceSelected != "สถานที่ทั้งหมด" && this.provinceSelected != "") {
        this.filterProvince();
      }
      console.log(this.priceSelected != "กรุณาเลือก" && this.priceSelected != "ทั้งหมด" && this.priceSelected != "")
      if (this.priceSelected != "กรุณาเลือก" && this.priceSelected != "ทั้งหมด" && this.priceSelected != "") {
        this.filterPrice();
      }
    },
    updateProvinceSelected(selected) {
      this.provinceSelected = selected
      this.updateSearchText(this.selectedSearchText)
      if (this.provinceSelected == "สถานที่ทั้งหมด") {
        return;
      }

      this.filterProvince();
    },
    updatePriceSelected(selected) {
      this.priceSelected = selected
      this.updateSearchText(this.selectedSearchText)
      if (this.priceSelected == "ทั้งหมด") {
        return;
      }

      this.filterPrice();
    },
    filterProvince() {
      this.selectedMerchants = this.merchants.filter((selectMerchant) => {
        return this.provinceSelected == selectMerchant.addressProvinceName
      })
    },
    filterPrice() {
      this.selectedMerchants = this.merchants.filter((selectMerchant) => {
        if (selectMerchant.priceLevel == 1 && this.priceSelected != "ไม่เกิน 100 บาท") {
          return false;
        }
        if (selectMerchant.priceLevel == 2 && this.priceSelected != "100 - 300 บาท") {
          return false;
        }
        if (selectMerchant.priceLevel == 3 && this.priceSelected != "300 - 600 บาท") {
          return false;
        }
        if (selectMerchant.priceLevel == 4 && this.priceSelected != "มากกว่า 600 บาท") {
          return false;
        }
        return true;
      })
    }
  },
}
</script>

<style>
.body-container {
  margin: 20px 10px;
}
</style>
