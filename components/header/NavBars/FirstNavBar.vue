<template>
  <b-nav tabs align="center" class="header">
    <b-navbar-brand href="#" class="col-12 d-flex">
      <div class="row col-12 align-items-center">
        <div class="col-lg-3 col-md-2 col-sm-2 col-3">
          <img
            class="d-none d-md-block"
            src="https://search-merchant.คนละครึ่ง.com/images/halfhalf-logo.png"
          />
          <img
            class="d-md-none col-xs-12"
            src="https://search-merchant.คนละครึ่ง.com/images/halfhalf-logo-mini.png"
          />
        </div>

        <div class="col-lg-9 col-md-10 d-none d-md-block search-container">
          <div class="row">
            <div class="col-lg-3 col-md-4"></div>
            <div class="col-lg-6 col-md-5">
              <input
                class="form-control my-0 py-1 red-border"
                type="text"
                placeholder="ค้นหา ชื่อ ร้านอาหาร และเครื่องดื่ม ร้านธงฟ้า ร้านค้า OTOP และสินค้าทั่วไป"
                aria-label="Search"
              />
            </div>
            <span class="col-2 input-group-text red lighten-3" id="basic-text1"
              ><i class="fas fa-search text-grey" aria-hidden="true"></i
            ></span>
          </div>
        </div>

        <div class="col-sm-10 col-9 d-md-none">
          <div class="col-12">
            <input
              class="form-control my-0 py-1 red-border"
              type="text"
              placeholder="ค้นหา ชื่อ ร้านอาหาร และเครื่องดื่ม ร้านธงฟ้า ร้านค้า OTOP และสินค้าทั่วไป"
              aria-label="Search"
            />
          </div>
        </div>
      </div>
    </b-navbar-brand>
  </b-nav>
</template>

<script>
export default {
  name: 'FirstNavBar',
}
</script>

<style>
.custom-bg-dark-blue {
  background-color: #293a7c;
}

.row {
  padding: 0;
  margin: 0;
}

.input-border-a {
  border: 1px solid #ffca28;
}

.header {
  display: inline;
}

.grey-search-bar {
  border-radius: 6%;
}
</style>