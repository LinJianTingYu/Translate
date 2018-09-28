<template>
  <div class="translate">
  	<h2>{{translatedtext}}</h2>
  </div>
</template>

<script>
export default {
  name: 'translate',
  props:["translatedtext"],
  data () {
    return {
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
