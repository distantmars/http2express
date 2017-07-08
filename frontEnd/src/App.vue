<template>
  <div id="app">
    <img src="./assets/14.png">
    <img v-for="image in images" :src="image">
  </div>
</template>

<script>
import jsonp from "jsonp"
export default {
  name: 'app',
  data () {
    return {
      images:[]
    }
  },
  created: function() {
    // jsonp("https://api.douban.com/v2/movie/top250?count=200", null, (err, data) => {
    //   if (err)
    //     console.error(err)
    //   else {
    //     data.subjects.forEach((val,index) => {
    //         this.images.push(val.images.large)
    //     })
    //     console.log(this.images)
    //   }
    // })
    for (let i = 1; i < 27; i++) {
      this.images.push("/" + i + ".jpg")
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
