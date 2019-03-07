<template>
  <div id="app" class="main">
    <div class="container">
    <app-aside></app-aside>
      <div class="container__inner">
        <app-header></app-header>
        <app-contnent></app-contnent>

      </div>
      <app-comments></app-comments>
    </div>
  </div>
</template>

<script>

import Aside from './Aside.vue'
import Header from './Header.vue'
import Content from './Content.vue'
import Comments from './Comments.vue'
export default {
  name: 'app',
  data () {
    return {

    };


  },
  components:{
    AppAside: Aside,
    AppHeader: Header,
    AppContnent: Content,
    AppComments: Comments
  }
}
</script>

<style lang="sass">
#app
  font-family: 'Avenir', Helvetica, Arial, sans-serif

a
  text-decoration: none
.main
  background-color: #f9f9fa
.container
  margin: 0 auto
  display: flex
  width: 1280px
  overflow-x: hidden
  position: relative
  @media (max-width: 1280px)
    width: 100%

.container__inner
  width: 990px
  @media (max-width: 1280px)
    width: 100%
  @media (max-width: 1024px)
    width: calc(100% - 290px)
  @media(max-width: 768px)
    width: 100%

</style>
