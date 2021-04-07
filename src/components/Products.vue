<template>
  <div v-if="productList.length > 0">
    <h3 class="text-center">Eklenen Ürünlerin Listesi</h3>
    <hr />
    <div class="row product-container">
      <productComponent v-for="(product, index) in productList" :key="index">
        <img class="card-img-top" :src="product.productImage" alt="Card image cap" />
        <div class="card-body">
          <h5 class="card-title">{{product.productName}}</h5>
          <small> <strong>Adet : </strong>{{product.productCount}}</small>
          <br />
          <small> <strong>Fiyat : </strong>{{product.productPrice}}</small>
          <br />
          <small> <strong>Tutar : </strong>{{product.productTotalPrice}}</small>
        </div>
      </productComponent>
    </div>
  </div>
</template>

<script>
  import Product from "./Product"
  import eventBus from "../eventBus"
  export default {
    components: {
      productComponent: Product
    },
    data() {
      return {
        productList: [],
      }
    },
    created() {
      eventBus.$on("addedProduct", (product) => {
        if (this.productList.length < 10) {
          this.productList.push(product)
          eventBus.$emit("productListLength", this.productList.length)
        } else {
          alert("Daha Fazla Ürün Ekleyemezsiniz....")
        }

      })
    }
  }

</script>
