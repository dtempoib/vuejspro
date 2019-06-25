<template>
        <ul class="list-group">
          
          <li v-for="(item, index) in items" :key="index" class="list-group-item">
          {{ item.title }}
          <button class="btn btn-sm btn-danger" @click="removeItem(index)" >-</button>
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
  },
  methods: {
    removeItem(index){
      this.$emit('itemRemove', index)
    }
  }
}
</script>

<style>

</style>
