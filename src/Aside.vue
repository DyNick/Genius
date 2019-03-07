<template>
  <aside v-bind:class="{ active: isOpen}">
    <button class="menu-button" v-bind:class="{ active: isOpen}" @click="toggle" >{{openerText}}</button>
    <div class="user-block">
      <img class="user-block__image" src="./assets/user.jpg" alt="user" >
      <div class="user-block__about">
        <div class="user-block__about__name">Lucas Douglas</div>
        <div class="user-block__about__mail">lucasduglas@upmitt.com</div>
      </div>
    </div>
    <nav>
      <ul class="navigation__list">
        <li class="navigation__list__item navigation__list__item--active"><a href="#" class="navigation__list__item__link">Candidates</a></li>
        <li class="navigation__list__item"><a href="#" class="navigation__list__item__link">Companies</a></li>
        <li class="navigation__list__item"><a href="#" class="navigation__list__item__link">Contacts</a></li>
        <li class="navigation__list__item"><a href="#" class="navigation__list__item__link">Missions</a></li>
        <li class="navigation__list__item navigation__list__item--margin"><a href="#" class="navigation__list__item__link">Users</a></li>
        <li class="navigation__list__item"><a href="#" class="navigation__list__item__link">Import</a></li>
      </ul>
    </nav>
    <div class="logo-box">
      <img src="./assets/logo-main-first-part.jpg" alt="logo" class="logo-box__first-part">
      <img src="./assets/logo-main-second-part.jpg" alt="logo" class="logo-box__second-part">
    </div>

  </aside>

</template>

<style lang="sass">

a
  text-decoration: none


aside
  width: 290px
  position: relative
  background-image: url(./assets/bg.jpg)
  background-repeat: no-repeat
  background-size: cover


  @media(max-width: 768px)
    position: fixed
    top: 0
    left: -290px
    transition: .3s
    bottom: 0
    z-index: 1
    &.active
      left: 0
      transition: .3s


.user-block
  background-color: rgba(255, 255, 255, 0.1)
  display: flex
  align-items: center
  justify-content: center
  height: 75px
  &__image
    width: 40px
    height: 40px
    border-radius: 50%
    border: 3px solid #fff

  &__about
    text-align: left
    margin-left: 20px
    &__name
      color: rgba(255, 255, 255, 0.7)
      font-weight: bold

    &__mail
      margin-top: 5px
      color: rgba(255, 255, 255, 0.7)
      font-size: 14px



.navigation__list
  display: flex
  flex-direction: column
  align-items: center
  margin-top: 40px
  overflow: hidden
  &__item
    width: 150px
    text-align: left
    height: 40px
    line-height: 40px
    position: relative
    font-size: 16px
    transition: .3s
    &:before
      content: ''
      height: 8px
      width: 60px
      border-bottom-right-radius: 4px
      border-top-right-radius: 4px
      background: yellow
      display: block
      position: absolute
      left: -134px
      transition: .3s
      top: 16px

    &:after
      content: ''
      height: 8px
      width: 8px
      border-radius: 50%
      background: yellow
      display: block
      position: absolute
      left: -84px
      transition: .3s
      top: 16px

    &:hover
      font-size: 24px
      transition: .3s
      &:before
        left: -100px
        transition: .3s

      &:after
        left: -34px
        transition: .3s



    &--margin
      margin-top: 40px

    &__link
      color: #fff
      font-weight: bold



.logo-box
  position: absolute
  bottom: 30px
  left: 50%
  transform: translateX(-50%)
  display: flex
  flex-direction: column
  align-items: center
  justify-content: center

  &__first-part
    width: 70px

  &__second-part
    width: 145px

.menu-button
  display: none
  position: absolute
  right: -60px
  top: 5px
  color: #fff
  background: #140933
  border: none
  font-weight: bold
  padding: 8px
  @media(max-width: 768px)
    display: block
</style>

<script>
  export default {

    data() {
      return {
        openerText: 'menu',
        isOpen: false
      }
    },
    methods: {
      open() {
        this.openerText = 'menu';
        this.isOpen = true;
      },
      close() {
        this.openerText = 'menu';
        this.isOpen = false;
      },
      toggle() {
        if (this.isOpen) {
          this.close();
        } else {
          this.open();
        }
      }
    }
  }
</script>

