<template>
  <div class="container">
    <div class="card center">
      <h3>Actually news {{ date }} </h3>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      date: new Date().toLocaleDateString()

    }
  }
}
</script>

<style>

</style>
