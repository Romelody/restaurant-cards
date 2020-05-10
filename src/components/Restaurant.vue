<template>
    <div id="restaurant" >
        <div class="restaurant" >
          <h3>{{name}}</h3>
          <p>{{type}}</p>
          <p>⋆ {{rating}}</p>
        </div>
    </div>
</template>

<script>
export default {
  name: 'Restaurant',
  props: {
    name: String,
    type: String,
    rating: Number
  }
}
</script>

<style>

#restaurant{
    background: #FFB74D;
    border-radius: 30px;
    width: 100%;
    margin: 10px;
    padding: 30px;
    color: #E64A19;
}

</style>
