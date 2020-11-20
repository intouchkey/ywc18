<template>
  <div class="facility-container">
    <div class="circle-tag image1" v-if="facilities.includes('ที่จอดรถ')"></div>
    <div
      class="circle-tag image2"
      v-if="facilities.includes('รับจองล่วงหน้า')"
    ></div>
    <div
      class="circle-tag image3"
      v-if="facilities.includes('สามารถนำสัตว์เลี้ยงเข้าได้')"
    ></div>
  </div>
</template>

<script>
export default {
  name: 'FacilitiesSection',
  props: ['facilities'],
}
</script>

<style>
.facility-container {
  margin-top: 3%;
}
.circle-tag {
  display: inline-block;
  width: 40px;
  height: 40px;
  -moz-border-radius: 20px;
  -webkit-border-radius: 20px;
  background-position: 50% 50%;
  background-repeat: no-repeat;
  background-size: 25px 25px;
  border: 1px solid #77c36b;
}
.image1 {
  background-image: url('https://search-merchant.xn--42caj4e6bk1f5b1j.com/images/facilities/%E0%B8%97%E0%B8%B5%E0%B9%88%E0%B8%88%E0%B8%AD%E0%B8%94%E0%B8%A3%E0%B8%96.png');
}
.image2 {
  background-image: url('https://search-merchant.xn--42caj4e6bk1f5b1j.com/images/facilities/%E0%B8%A3%E0%B8%B1%E0%B8%9A%E0%B8%88%E0%B8%AD%E0%B8%87%E0%B8%A5%E0%B9%88%E0%B8%A7%E0%B8%87%E0%B8%AB%E0%B8%99%E0%B9%89%E0%B8%B2.png');
}
.image3 {
  background-image: url('https://search-merchant.xn--42caj4e6bk1f5b1j.com/images/facilities/%E0%B8%AA%E0%B8%B2%E0%B8%A1%E0%B8%B2%E0%B8%A3%E0%B8%96%E0%B8%99%E0%B8%B3%E0%B8%AA%E0%B8%B1%E0%B8%95%E0%B8%A7%E0%B9%8C%E0%B9%80%E0%B8%A5%E0%B8%B5%E0%B9%89%E0%B8%A2%E0%B8%87%E0%B9%80%E0%B8%82%E0%B9%89%E0%B8%B2%E0%B9%84%E0%B8%94%E0%B9%89.png');
}
</style>
