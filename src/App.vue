<template>
  <div id="nav">
    
  </div>
  <router-view/>
</template>

<script>
import axios from 'axios'

export default {
  name : 'App',
  beforeCreate(){
    this.$store.commit('initializeStore')
    const token = this.$store.state.token

    if (token){
      axios.defaults.headers.common['Authorization'] = 'Token '+ token
    }
    else{
      axios.defaults.headers.common['Authorization'] = ''
    }
  }
}
</script>

<style lang="scss">
*{
  h1, h2, h3, h4, h5, h6, p, a, span{
    font-family: 'Charis SIL', serif;
    font-family: 'Karla', sans-serif;
    font-family: 'Merriweather', serif;
    font-family: 'Roboto', sans-serif;
    font-family: 'Roboto Slab', serif;
    font-family: 'Stoke', serif;
}
}
</style>
