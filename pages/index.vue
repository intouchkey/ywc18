<template>
  <div class="main-container">
    <Header :provinces="provinces"></Header>
    <Body
      :categories="categories"
      :subcategories="subcategories"
      :priceRange="priceRange"
      :provinces="provinces"
      :merchants="merchants"
    ></Body>
  </div>
</template>

<script>
export default {
  name: 'index',

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
      this.provinces = ['สถานที่ทั้งหมด'].concat(
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
.main-container {
  font-family: IBM Plex Sans Thai, sans-serif;
  background-image: url('https://search-merchant.xn--42caj4e6bk1f5b1j.com/images/result-bg.png');
  background-repeat: no-repeat;
  background-attachment: scroll;
  background-size: cover;
}
</style>
