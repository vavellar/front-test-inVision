<template>
    <div class="card-box">
        <div class="products-card">
            <tr class="products" v-for="produto of produtos" :key="produto.id">
                <img class="img" style="height: 100px; width: 100px" :src="produto.product.imageObjects.large"/> 
                <td class="name"> {{ produto.product.name}} </td>  
                <td class="price"> {{ produto.product.priceSpecification.price | real  }} </td> 
            </tr>
        </div>
    </div>
</template>

<script>
import Produto from '../services/produtos'
export default {
    data() {
        return {
            produtos: []
        }
    },
    mounted() {
        Produto.listar().then(resp => {
            this.produtos = resp.data.items
            console.log(this.produtos)
        })
    }

}
</script>

<style>

.card-box {
    display: flex;
    background-color: white;
    margin: 0px 10px;
    border: 1px solid white;
    border-radius: 4px;
    height: 100%;
    width: 100%;
    margin-top: 10px;
}

.products {
    display: flex;
    flex-direction: row;
    border: 1px solid rgb(214, 206, 206);
    margin-bottom: 10px;
    padding: 10px;
}

.price {
    align-self: flex-end;
    font-weight: 700;
    justify-content: flex-end;
}

.name, .img {
    margin-left: 20px;
}

@media (min-width: 895px) {  
  .products-card {
    display: flex;
    justify-content: center;
    flex-direction: column;
    width: 100%;
  }

  .card-box {
      display: flex;
      justify-content: center;
  }

  .price {
      display: flex;
      justify-content: flex-end;
  }
}




</style>