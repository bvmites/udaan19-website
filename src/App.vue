<template>
    <div id="app">
        <!-- CURSOR -->
        <!--<div class="cursor"></div>-->
        <loadingComponent v-if="!loaded"></loadingComponent>
        <menuComponent></menuComponent>
        <router-view/>
    </div>
</template>

<script>
  import menuComponent from './components/menuComponent'
  import loadingComponent from './components/loadingComponent'


  export default {
    name: 'app',
    components: {
      menuComponent,
      loadingComponent
    },
    data() {
      return {
        loaded: false
      }
    },
    mounted() {

      let self = this
      window.onload = function() {
        self.loaded = true
      }


      /*let cursor = document.querySelector('.cursor')
      document.addEventListener('mousemove', function (e) {
        cursor.setAttribute("style", "top:" + e.pageY + "px; left:" + e.pageX + "px;")
      })

      document.addEventListener('click', function (e) {
        cursor.classList.add('click')

        setTimeout(() => {
          cursor.classList.remove('click')
        }, 500)
      })*/
    }
  }
</script>

<style lang="sass">
    @import ./sass/app
</style>
