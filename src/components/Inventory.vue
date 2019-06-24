

<template>
        <div class="row">
                <div v-for="(item, index) in items" class="card" style="width: 17rem;">
                  <img class="card-img-top" :src="item.photo" alt="Card image cap">
                  <div class="card-body">
                    <h5 class="card-title"> {{ item.title }} </h5>
                    <p class="card-text"> {{ item.price }} </p>
                    <a href="#" class="btn btn-primary"> + Add </a>
                  </div>
                </div>

                

              
            </div>
</template>
<script>
export default {
props: ['items']
}
</script>

<style>

</style>
            