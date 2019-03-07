<template>
  <div class="comments" v-bind:class="{ active: isOpen}">
    <button class="comments__button" @click="toggle" v-bind:class="{ active: isOpen}"><i class="fas fa-chevron-left"></i></button>
    <h2 class="comments__title">Comments</h2>
    <div class="comments__panel">
      <div class="cssselect">
        <select name="" id="">
          <option value=""> 12</option>
          <option value=""> 13</option>
          <option value=""> 14</option>
          <option value=""> 15</option>
        </select>
      </div>
      <button class="text-align-italic button-text"><i class="fas fa-underline"></i></button>
      <button class="text-align-italic  button-text"><i class="fas fa-bold"></i></button>
      <button class="text-align-italic  button-text"><i class="fas fa-italic"></i></button>
      <button class="text-align-center  button-text"><i class="fas fa-align-center"></i></button>
      <button class="text-align-left button-text"><i class="fas fa-align-left"></i></button>
      <button class="text-align-right  button-text"><i class="fas fa-align-right"></i></button>
    </div>
    <div class="comments__text">
      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Aspernatur, magnam molestias. Alias asperiores assumenda beatae commodi est molestias necessitatibus tenetur. Aspernatur blanditiis fuga molestias nam neque possimus qui repellendus? Accusantium!
    </div>

    <button class="comments__update">update candidat</button>
  </div>
</template>

<script>
  export default {

    data() {
      return {
        openerText: 'Open',
        isOpen: false
      }
    },
    methods: {
      open() {
        this.openerText = 'Close';
        this.isOpen = true;
      },
      close() {
        this.openerText = 'Open';
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

<style lang="sass">
.comments
  display: block
  position: absolute
  width: 410px
  background-color: #fff
  top: 0
  bottom: 0
  right: calc(-410px + 20px)
  box-shadow: 1px 3px 30px 0px rgba(0, 0, 0, 0.28)
  transition: .5s
  padding: 25px 45px
  box-sizing: border-box
  @media (max-width: 480px)
    width: 300px
    right: calc(-300px + 20px)
  &.active
    transition: .5s
    right: 0

  &__title
    font-size: 24px
    color: #c9cdd8
    font-weight: bold
    text-align: center
    margin: 20px 0
  &__panel
    display: flex
    align-items: center
    justify-content: space-around
    margin-bottom: 20px
  &__text
    line-height: 1.7
    font-size: 15px
  &__update
    width: 200px
    height: 46px
    border: none
    border-radius: 23px
    text-transform: uppercase
    font-weight: bold
    background-color: #00c3dc
    color: #fff
    position: absolute
    bottom: 30px
    left: 50%
    transform: translateX(-50%)
    &:hover
      cursor: pointer
      background-color: #cecece

  &__button
    border: 2px solid #c9cdd8
    border-radius: 50%
    background-color: #fff
    height: 25px
    width: 25px
    text-align: center
    line-height: 23px
    padding: 0
    box-sizing: border-box
    color: #00c3dc
    transition: .5s
    outline: none
    position: absolute
    left: -13px
    top: 50px
    &:hover
      cursor: pointer
    &.active
      transform: rotate(180deg)
      transition: .5s


.cssselect
  position: relative
  display: inline-block
  vertical-align: top
  select
    background: #fff
    color: #000
    outline: none
    display: inline-block
    -webkit-appearance: none
    -moz-appearance: none
    appearance: none
    cursor: pointer
    width: 100%
    padding: 3px 30px 3px 10px
    z-index: 1
    border-radius: 4px
    border: 1px solid #272931
    text-transform: capitalize
    font-size: 13px
    color: #272931
    &::-ms-expand
      display: none
  &:after
    content: ''
    right: 6px
    top: 50%
    transform: translateY(-50%)
    display: block
    position: absolute
    width: 0
    height: 0
    border-style: solid
    border-width: 5px 5px 0 5px
    border-color: #fff transparent transparent transparent
  &:before
    content: ''
    right: 0px
    width: 22px
    height: 23px
    display: block
    position: absolute
    background-color: #272931
    border-bottom-right-radius: 4px
    border-top-right-radius: 4px

  &:empty
    display: none
.button-text
  border: none
  background-color: transparent
  color: #c9cdd9
</style>
