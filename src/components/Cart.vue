<template>
        <ul class="list-group">
          
          <li v-for="(item, index) in items" :key="index" class="list-group-item">
          {{ item.title }}
          {{ item.price }}
          </li>
          <li class="list-group-item">Total Price : {{ totalPrice }}</li>
        </ul>
</template>
<script>
export default {
  props: ['items'],
  computed: {
    totalPrice(){
      var total = 0
      this.items.forEach(item => {
        total += parseFloat(item.price)
      })
      return total
    }
  }
}
</script>

<style>

</style>
