<template>
  <div class="container">
    <h1 class="text-center">Ürün Ekleme Uygulaması</h1>
    <hr />
      <addNewProductComponent> </addNewProductComponent>
    <br /><br />
      <progressBarComponent></progressBarComponent>
    <br /><br />
   
      <productsComponent></productsComponent>
  </div>
</template>

<script>
import AddProduct from "./components/AddProduct";
import Progress from "./components/Progress";
import Products from "./components/Products";
export default {
  components: {
    addNewProductComponent : AddProduct,
    progressBarComponent : Progress,
    productsComponent : Products
  },
  
};
</script>

<style>
body {
  background-color: aliceblue;
  padding-top: 20px;
  padding-bottom: 20px;
}

.card {
  margin-right: 5px;
  margin-bottom: 5px;
}

.card:last-child {
  margin-right: 0px;
}

.col-md-2 {
  max-width: 15.666667% !important;
}

.product-container {
  margin-left: 15px;
}
</style>
