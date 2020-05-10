<template>
    <div id="restaurant" >
        <div class="restaurant" >
            {{name}}
        </div>
    </div>
</template>

<script>
export default {
  name: 'Restaurant',
  props: {
    name: String
  }
}
</script>

<style>
 #restaurant{
    display: flex;
    flex-direction: row;
 }

.restaurant{
    width: 33%;
    height: 300px;
    background: powderblue;
    border-radius: 30px;

}

</style>
