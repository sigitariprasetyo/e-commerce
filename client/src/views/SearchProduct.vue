<template>
<div>
    <Navbar></Navbar>
    <div class="box-product">
        <p class="title">Results</p>
          <div v-if="products.length > 0">
            <div class="container box">
              <div v-for="(product, i) in products" :key="i" class="row">
                  <CardProduct :product="product" class="card"></CardProduct>
              </div>
            </div>
          </div>
          <div v-else>
              <div class="notFound"><i class="fas fa-exclamation-triangle"></i> Sorry Product not found!</div>
          </div>
    </div>
</div>
</template>

<script>
import Navbar from '../components/Navbar'
import CardProduct from '../views/CardProduct'

export default {
  name: 'searchProduct',
  components: {
    Navbar,
    CardProduct
  },
  computed: {
    products: {
      get () {
        return this.$store.state.searchProduct
      }
    }
  },
  watch: {
    products () {}
  }
}
</script>
<style scoped>
.box-product {
    margin-top: 50px;
    margin-left: 10%;
    margin-right: 10%;
    margin-bottom: 50px;
}
.container {
    display: flex ;
    flex-wrap: wrap;
    justify-content: flex-start;
}
.card {
    margin-top: 100px;
    height: 430px;
    width: 300px;
    overflow: hidden;
    margin: 20px;
    box-shadow: 0 4px 5px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
}
.notFound {
    font-size: 25px;
    color: #d71149;
}
</style>
