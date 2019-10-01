<template>
  <div>
    <Nav />
    <Home />
  </div>
</template>

<script>
import Nav from '~/components/Nav.vue'
import Home from '~/components/Home.vue'

export default {
  components: {
    Nav,
    Home
  },
  created() {
    console.log(process.env.API_URL)
  }
}
</script>
