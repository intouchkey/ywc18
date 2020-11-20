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

  data() {
    return {
      categories: ['ทั้งหมด'],
      subcategories: {},
      priceRange: [],
      provinces: [],
      merchants: [],
    }
  },

  async fetch() {
    const data = await fetch('https://panjs.com/ywc18.json').then((res) =>
      res.json()
    )

    this.mapData(data)
  },

  methods: {
    mapData: function (data) {
      data.categories.forEach((category) => {
        this.categories.push(category.name)
        this.subcategories[category.name] = ['ทั้งหมด'].concat(
          category.subcategories
        )
        this.subcategories[category.name] = [
          ...new Set(this.subcategories[category.name]),
        ]
      })

      this.priceRange = ['ทั้งหมด'].concat(data.priceRange)
      this.provinces = ['พื้นที่ไกล้ฉัน', 'สถานที่ทั้งหมด'].concat(
        data.provinces
      )
      this.merchants = data.merchants

      this.merchants.forEach((merchant) => {
        let bathString = '   |   '

        for (let i = 0; i < 4; i++) {
          if (i < merchant.priceLevel) {
            bathString += '<strong class="black">฿</strong>'
          } else {
            bathString += '฿'
          }
        }

        merchant.fullDescription =
          merchant.subcategoryName +
          bathString +
          '   |   ' +
          merchant.addressDistrictName +
          ' ' +
          merchant.addressProvinceName
      })
    },
  },
}
</script>

<style>
.body-container {
  margin: 20px 10px;
}
</style>
