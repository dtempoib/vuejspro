<template>
  <div id="app">
      <navbar></navbar>
  <div class="container">
    <div class="row">
      <div class="col-sm-9">
          <Inventory @newItemAdded="addCartItem" :items="items" ></Inventory>
      </div>
      <div class="col-sm-3">
        <cart @itemRemove="removeItem" :items="cart" ></cart>
      </div>
    </div>
  </div>
       
    </div>
</template>

<script>
import Navbar from './components/Navbar'
import Cart from './components/Cart'
import Inventory from './components/Inventory'
import data from './data.js'

export default {
  components: {
    Navbar,
    Cart,
    Inventory
  },
  data(){
    return {
     items: [],
     cart: [ ]
    }
  },
  mounted(){
  this.items = data
  },
  methods: {
    addCartItem(item){
      this.cart.push(item)
    },
    removeItem(index){
      this.cart.splice(index, 1)
    }
  }
 }
</script>

<style>
.container { 
  padding-top: 10px;
}
</style>
