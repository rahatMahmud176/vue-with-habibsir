<template>
  <div id="app">
     <Navbar :key="$route.path"/>
    <router-view/>
    <Footer/> 
  </div>
</template>

<script>
import Navbar from '@/components/Includes/Navbar'
import Footer from '@/components/Includes/Footer'
export default {
  name: 'App',
  components: { Navbar,Footer }
}
</script>

<style>
 
</style>

 