<template>
      <header class="header">
        <div class="header-info-main">
          <div class="header-info">
            <div class="header-info__arrow">
                <i class="fas fa-angle-left header-info__arrow__left"></i>
              <span class="header-info__arrow__title">Candidates</span>
            </div>
            <div class="header-info__name">Christopher Smith</div>
            <div class="header-info__description">UI & UX Designer @ Upmitt</div>
          </div>
          <div class="header-info-more">
            <div class="header-info-more__field">
              <span class="header-info-more__field__description header-info-more__field__description--phone">06 56 44 31 22 </span>
              <span class="header-info-more__field__title">personal</span>
            </div>
            <div class="header-info-more__field">
              <span class="header-info-more__field__description ">cristhopersmith@gmail.com</span>
              <span class="header-info-more__field__title">personal</span>
            </div>
            <div class="header-info-more__field">
              <span class="header-info-more__field__description ">conact@gmail.com</span>
              <span class="header-info-more__field__title">proffesional</span>
            </div>

            <div class="header-info-more__field">
              https://www.linkedin.com/in/eleonoreceylayd/

            </div>

          </div>
        </div>
        <div class="navigation-header">
          <ul class="navigation-header__list">
            <li class="navigation-header__list__item"><a href="#" class="navigation-header__list__item__link">Profile</a></li>
            <li class="navigation-header__list__item"><a href="#" class="navigation-header__list__item__link">Tags</a></li>
            <li class="navigation-header__list__item"><a href="#" class="navigation-header__list__item__link">Resume</a></li>
            <li class="navigation-header__list__item"><a href="#" class="navigation-header__list__item__link">Documents</a></li>
          </ul>
        </div>
      </header>
</template>
<style lang="sass">

.header
  background-color: #fff
  padding: 0 25px
  box-sizing: border-box
  box-shadow: -1px 7px 28px -14px rgba(0, 0, 0, 0.48)

.header-info-main
  display: flex
  align-items: center
  justify-content: space-between
  @media (max-width: 768px)
    flex-direction: column
    align-items: flex-start


.header-info
  font-size: 20px
  @media (max-width: 768px)
    margin-top: 40px
  &__arrow
    color: #929ab2
    font-size: 14px
    margin: 15px 0

  &__name
    color: #140933
    font-size: 24px
    font-weight: bold
    margin-bottom: 5px

  &__description
    color: #00c3dc
    font-size: 15px
    font-weight: bold
    margin-bottom: 5px


.header-info-more
  display: flex
  flex-direction: column
  align-items: flex-end
  justify-content: center
  font-size: 13px
  color: #929ab2
  margin-right: 20px
  @media (max-width: 768px)
    align-items: flex-start
  &__field
    margin-bottom: 5px
    &:first-child
      margin-top: 15px
    &__description
      font-weight: bold
      &--phone
        font-size: 18px
    &__title
      font-style: italic

.navigation-header
  height: 55px
  display: flex
  align-items: flex-end
  &__list
    display: flex
    align-items: center
    justify-content: flex-start
    &__item
      margin-left: 50px
      text-transform: uppercase
      padding-bottom: 10px
      box-sizing: border-box
      overflow: hidden
      @media (max-width: 480px)
        margin-left: 20px
      &__link
        color: #bfbcc8
        font-weight: bold
        font-size: 14px
        padding-bottom: 10px
        position: relative
        transition: .3s
        box-sizing: border-box
        bottom: -1px
        &:before
          content: ''
          display: block
          height: 3px
          width: 100%
          background-color: #00c3dc
          position: absolute
          left: -100%
          bottom: 0
          transition: .3s
        &:hover
          color: #140933
          transition: .3s

          &:before
            left: 0
            transition: .3s
      &:first-child
        margin-left: 0
</style>
