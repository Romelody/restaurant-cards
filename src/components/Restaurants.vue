<template>
  <div id="restaurants" class="container">
    <h1>Restaurants</h1>
    <Restaurant
      v-for="restaurant in asian_restaurants"
      :name=restaurant.name
      :key="restaurant.id" />
  </div>
</template>

<script>
import Restaurant from './Restaurant.vue'
export default {
  components: {
    Restaurant
  },
  data () {
    return {
      asian_restaurants: [
        {
          name: 'Nobiru',
          rating: 4,
          type: 'Asian Food',
          id: '001'
        },
        {
          name: 'Nippori',
          rating: 5,
          type: 'Asian Food',
          id: '002'
        }
      ],
      burger_restaurants: [
        {
          name: 'Burger King',
          rating: 4,
          type: 'Burger',
          id: '004'
        },
        {
          name: 'Doggs',
          rating: 5,
          type: 'Burger',
          id: '003'
        }
      ]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container{
  width: 90%;
  height: 500px;
  margin: 0 auto;
  background: peachpuff;
  border-radius: 30px;
}

h1{
  padding: 30px;
  text-transform: uppercase;
}
</style>
