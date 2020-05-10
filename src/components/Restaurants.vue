<template>
<div id="restaurants">
  <div class="container buttons">
    <span class="button" @click="viewAsianRestaurant=true">Asian Food</span>
    <span class="button" @click="viewBurgerRestaurant=true">Burger Food</span>
  </div>

  <div class="container">
    <h1>Restaurants</h1>
    <div class="restaurants" v-show="viewAsianRestaurant">
      <Restaurant
        v-for="restaurant in assian_restaurants"
        :name=restaurant.name
        :rating=restaurant.rating
        :type=restaurant.type
        :key="restaurant.id" />
    </div>
    <!-- <div >
      <p>No hay Restaurantes</p>
    </div> -->
    <div class="restaurants" v-show="viewBurgerRestaurant">
      <Restaurant
      v-for="restaurant in burger_restaurants"
      :name=restaurant.name
      :rating=restaurant.rating
      :type=restaurant.type
      :key="restaurant.id" />
    </div>
  </div>
</div>

</template>

<script>
import axios from 'axios'
import Restaurant from './Restaurant.vue'

export default {
  components: {
    Restaurant
  },
  data () {
    return {
      assian_restaurants: [],
      burger_restaurants: [],
      viewAsianRestaurant: true,
      viewBurgerRestaurant: true
      // asian_restaurants: [
      //   {
      //     name: 'Nobiru',
      //     rating: 4,
      //     type: 'Asian Food',
      //     id: '001'
      //   },
      //   {
      //     name: 'Nippori',
      //     rating: 5,
      //     type: 'Asian Food',
      //     id: '002'
      //   }
      // ],
      // burger_restaurants: [
      //   {
      //     name: 'Burger King',
      //     rating: 4,
      //     type: 'Burger',
      //     id: '004'
      //   },
      //   {
      //     name: 'Doggs',
      //     rating: 5,
      //     type: 'Burger',
      //     id: '003'
      //   }
      // ]
    }
  },
  mounted () {
    axios
      .get('https://b3a1b467.ngrok.io/restaurants')
      .then(response => response.data)
      .then(data => {
        (this.assian_restaurants = data.assian_restaurants);
        (this.burger_restaurants = data.burger_restaurants)
      })
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.restaurants{
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  margin: 0 auto;
}

.container{
  width: 90%;
  height: 100%;
  margin: 0 auto;
  margin-bottom: 20px;
  background: #FFF59D;
  border-radius: 30px;
  padding: 30px;
}

h1{
  padding: 30px;
  text-transform: uppercase;
  color: #E64A19;
}

.buttons{
  display: flex;
  flex-direction: row;
  justify-content: flex-end;
}

.button{
  margin: 0 10px;
  background: #E64A19;
  padding: 10px;
  border-radius: 10px;
  color: #fff;
  cursor: pointer;
}

.button:hover{
  background: #fff;
  color:  #E64A19;
}

</style>
