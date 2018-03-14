<template>
  <div id="app">
    <router-view/>
    <app-footer></app-footer>
  </div>
</template>

<script>
import Footer from '@/components/Footer'
export default {
  name: 'App',
  components: {
    'app-footer': Footer
  }
}
</script>


