<script setup>
  import axios from 'axios'
  import {ref} from 'vue'

  const joke = ref('')

//  using axios
  // axios.get('https://api.chucknorris.io/jokes/random')
  //   .then(res => {
  //     joke.value = res.data.value
  //   })

// using try catch await
  const jokeApi = async() => {
    try {
      const res = await axios.get('https://api.chucknorris.io/jokes/random')
      joke.value = res.data.value
    } catch(err) {
      console.log(err)
    }
  }
  jokeApi()

</script>

<template>
  <h1>Hello</h1>
  <h3>{{ joke }}</h3>
</template>

<style>

</style>
