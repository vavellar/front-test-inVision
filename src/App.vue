<template>
  <body>
    <div class="app">
      <Header/>
      <div class="title">
        <p class="title-title">Produtos</p>
      </div>
      <div class="card-box-products">
        <Products/>
      </div>
      <div class="cart">
        <Cart/>
      </div>
      <div class="button">
        <Button/>
      </div>
    </div>
    
  </body>
</template>

<script>
import Button from './components/Button.vue'
import Products from './components/Products.vue'
import Header from './components/Header.vue'
import Cart from './components/Cart.vue'
export default {
  components: {
     Header, Products, Cart, Button
  },
  data() {
    return {
      info: null
    }
  },

}
</script>

<style>

body {
  background-color: #EEEEEE;
  margin: 0;
}

.card-box-products {
  display: flex;
  background-color: white;
  box-shadow: 5px 5px 5px 5px #D7D7DA;
  margin: 0px 10px;
  border: 1px solid white;
  border-radius: 4px;
  height: 100%;
  margin-top:0px;
}

.title-title {
  margin-left: 20px;
  font-weight: 700;
  color: #A9A9A9
}




</style>