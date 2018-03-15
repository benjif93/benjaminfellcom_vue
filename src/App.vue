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

<style lang="scss">

  @import "src/styles/normalize";

  // Mainly text
  $a_color: #ffffff;
  $b_color: #333333;
  $c_color: #337ab7;
  $d_color: #777777;
  // Mainly Backgrounds
  $e_color: #00A8E8;
  $f_color: #007EA7;
  $g_color: #003459;

  // Text
  .txt-white {
    color: $a_color
  }
  
  .txt-black {
    color: $b_color
  }

  .txt-blue {
    color: $c_color
  }

  .txt-gray {
    color: $d_color
  }

  // Backgrounds
  .bg-white {
    background: $a_color
  }

  .bg-primary {
    background: $e_color;
  }

  .bg-secondary {
    background: $f_color;
  }

  .bg-tertiary {
    background: $g_color;
  }

  // Container 
  *::before,
  *::after {
    box-sizing: border-box;
  }

  .container {
    margin-right: auto;
    margin-left: auto;
    padding-right: 15px;
    padding-left: 15px;

    &::before,
    &::after {
      content: " ";
      display: table;
    }
  }

  .row {
    margin-left: -15px;
    margin-right: -15px;
  }

  .center-elem {
    margin: 0 auto;
  }

  // Flex stuff
  .flex {
    display: flex;
  }

  .flex-wrap {
    flex-wrap: wrap;
  }

  // List
  ul {
    padding-left: 25px;
    list-style-type: initial;

    li {

    }
  }

</style>
