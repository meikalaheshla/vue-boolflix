<template>
  <div id="app">
    <input type="text"><button>cerca</button>
    <div>
      <h2>FILM</h2>
      <ul>
        <li></li>
      </ul>
    </div>
  </div>
</template>

<script>


export default {
  name: 'App',
  components: {

  }, data() {
    return {
      films: [],
      searchTxt: "",
    }
  }, methods: {

  }

}
</script>

<style lang="scss">
</style>
