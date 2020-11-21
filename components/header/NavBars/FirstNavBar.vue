<template>
  <b-nav tabs align="center" class="header">
    <b-navbar-brand href="#" class="col-12 d-flex">
      <div class="row col-12 align-items-center">
        <div class="col-lg-3 col-md-2 col-sm-2 col-3">
          <img
            class="d-none d-md-block full-logo"
            src="https://search-merchant.คนละครึ่ง.com/images/halfhalf-logo.png"
          />
          <img
            class="d-md-none col-xs-12 small-logo"
            src="https://search-merchant.คนละครึ่ง.com/images/halfhalf-logo-mini.png"
          />
        </div>

        <div class="col-lg-9 col-md-10 d-none d-md-block search-container">
          <div class="row">
            <div class="col-lg-3 col-md-4 no-pd">
              <select text="พื้นที่ไกล้ฉัน" class="select-box">
                <option class="first-op" value="" disabled selected>
                  พื้นที่ไกล้ฉัน
                </option>
                <option
                  v-for="province in provinces"
                  :key="province"
                  :name="province"
                >
                  {{ province }}
                </option>
              </select>
            </div>
            <div class="col-lg-6 col-md-5 select-box-container">
              <input
                class="form-control my-0 py-1 red-border search-bar"
                type="text"
                placeholder="ค้นหา ชื่อ ร้านอาหาร และเครื่องดื่ม ร้านธงฟ้า ร้านค้า OTOP และสินค้าทั่วไป"
                aria-label="Search"
              />
            </div>
            <span
              class="col-1 input-group-text red lighten-3 grey-search-bar"
            ></span>
          </div>
        </div>

        <div class="col-sm-10 col-9 d-md-none no-pd">
          <div class="col-12 search-bar-filter-container">
            <input
              class="form-control my-0 py-1 red-border search-bar"
              type="text"
              placeholder="ค้นหา ชื่อ ร้านอาหาร และเครื่องดื่ม ร้านธงฟ้า ร้านค้า OTOP และสินค้าทั่วไป"
              aria-label="Search"
            />
            <span
              class="col-1 input-group-text red lighten-3 grey-search-bar"
            ></span>
            <img
              class="filter-image"
              src="https://search-merchant.xn--42caj4e6bk1f5b1j.com/images/filter.png"
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
  props: ['provinces'],
}
</script>

<style>
.select-box-container {
  padding: 0px;
}
.select-box {
  border-radius: 10px 0px 0px 10px;
  border-right: none;
  border-color: #ced4da;
  padding-left: 10px;
  font-size: 15px;
  height: 100%;
}

.custom-bg-dark-blue {
  background-color: #293a7c;
}

.no-pd {
  padding: 0px;
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

.search-bar {
  border-radius: 0px;
  border-right: none;
}

.grey-search-bar {
  border-radius: 0px 10px 10px 0px;
  background-color: #f8f8f8;
  border-left: none;
  background-image: url('~assets/search.png');
  background-position: 50% 50%;
  background-repeat: no-repeat;
  background-size: 15px 15px;
}

.full-logo {
  width: 160px;
  margin-left: 25%;
}

.small-logo {
  width: 60px;
}

.search-bar-filter-container {
  display: inline-flex;
}

.filter-image {
  -webkit-transform: scale(0.6);
  width: 20%;
}

@media screen and (max-width: 576px) {
  .search-bar {
    border-radius: 10px 0px 0px 10px;
    border-right: none;
  }
}
</style>
