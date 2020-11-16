<template>
    <b-nav tabs align="center" class="header">
        <b-navbar-brand href="#" class= "col-12 d-flex">
        <div class="row col-12 align-items-center">
            <div class="col-md-3 col-sm-2">
            <img class="d-none d-sm-block" src="https://search-merchant.คนละครึ่ง.com/images/halfhalf-logo.png">
            <img class="d-sm-none" src="https://search-merchant.คนละครึ่ง.com/images/halfhalf-logo-mini.png">
            </div>
            <div class="col-md-9 col-sm-10 search-container">
                <div class="col-3 d-none d-sm-block"> </div>
                <input class="col-md-7  form-control my-0 py-1 red-border" type="text" placeholder="ค้นหา ชื่อ ร้านอาหาร และเครื่องดื่ม ร้านธงฟ้า ร้านค้า OTOP และสินค้าทั่วไป" aria-label="Search">
                <span class="input-group-text red lighten-3 col-2" id="basic-text1"><i class="fas fa-search text-grey"
                    aria-hidden="true"></i></span>
            
            </div>
        </div>
        </b-navbar-brand>
    </b-nav>
</template>

<script>
export default {
  name: "FirstNavBar",
};
</script>

<style>
.custom-bg-dark-blue {
  background-color: #293A7C; 
} 

.row{
  padding:0;
  margin:0;
}

.input-border-a {
  border: 1px solid #ffca28;
}

.header {
  display: inline;
}

.grey-search-bar {
  border-radius:6%; 
}
</style>
