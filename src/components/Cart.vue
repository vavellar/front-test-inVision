<template>
<div class="app-cart">
  <tr class="cart-items">
      <td class="title-cart">produtos</td>
      <td class="title-cart">frete</td>
      <td class="title-cart-discount">desconto</td>
      <td class="title-cart-total">total</td>
  </tr>
  <tr class="cart-value">
      <td class="title-cart">{{ carrinho.subTotal | real }}</td> 
      <td class="title-cart">{{ carrinho.shippingTotal | real }}</td> 
      <td class="title-cart-discount">- {{ carrinho.discount | real }}</td> 
      <td class="title-cart-total">{{ carrinho.total | real }}</td> 
  </tr>
</div>
</template>

<script>
import Produto from '../services/produtos'
export default {
    data() {
        return {
            carrinho: []
        }
    },
    mounted() {
        Produto.listar().then(resp => {
            console.log(resp.data)
            this.carrinho = resp.data
        })
    },
}
</script>

<style>

.app-cart {
    display: flex;
    justify-content: space-between;
    border: 1px solid #D6CECE;
    margin: 20px 10px;
    padding: 10px;
    border-radius: 4px;
}

.cart-items, .cart-value{
    display: flex;
    flex-direction: column;
}

.title-cart, .title-cart-discount, .title-cart-total {
    margin-bottom: 10px;
    text-transform: uppercase;
}

.title-cart-discount {
    color: #FE6C00;
}

.title-cart-total {
    margin-top: 10px;
    font-weight: 700;
}


</style>