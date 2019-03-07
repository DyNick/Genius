<template>
   <div class="content"><!--content-->

      <div class="content__about">

        <div class="experience"><!--experience-->

          <div class="experience__title">
            <span class="experience__title__text">experience</span>
            <span class="experience__title__years">12 years</span>
          </div>

          <div class="experience__box">
              <div class="experience-item" v-for="(item,pIndex) in toBeShown" :key="pIndex" >

                <div class="experience-item__info">
                  <img src="./assets/company1.jpg" alt="company-1" class="experience-item__img">
                  <div class="experience-item__description">
                    <span class="experience-item__description__position">{{item.position}}</span>
                    <span class="experience-item__description__company">{{item.company}}</span>
                    <span class="experience-item__description__location">{{item.location}} </span>
                  </div>
                </div>

                <div class="experience-item__date">{{item.date}}</div>


              </div>
            <button class="show-more"  @click="prevPage" v-bind:class="{ notactive: currentPage==1}">
              <span class="show-more__text">Show Less</span>
              <i class="fas fa-angle-up"></i>
            </button>
            <button class="show-more" @click="nextPage" v-bind:class="{ notactive: currentPage == totalPages}">
              <span class="show-more__text">Show 2 more</span>
              <i class="fas fa-angle-down"></i>
            </button>
          </div>




        </div><!--/experience-->
        <div class="experience"><!--formation-->

          <div class="experience__title">
            <span class="experience__title__text">formation</span>
            <span class="experience__title__years"></span>
          </div>

          <div class="experience__box">
            <div class="experience-item" v-for="(item,pIndex) in toBeShownFormation" :key="pIndex" >

              <div class="experience-item__info">
                <img src="./assets/company3.jpg"  alt="company-1" class="experience-item__img">
                <div class="experience-item__description">
                  <span class="experience-item__description__position">{{item.position}}</span>
                  <span class="experience-item__description__company">{{item.company}}</span>
                  <span class="experience-item__description__location">{{item.location}} </span>
                </div>
              </div>

              <div class="experience-item__date">{{item.date}}</div>


            </div>
            <button class="show-more"  @click="prevPageFormation" v-bind:class="{ notactive: currentPageFormation==1}">
              <span class="show-more__text">Show Less</span>
              <i class="fas fa-angle-up"></i>
            </button>
            <button class="show-more" @click="nextPageFormation" v-bind:class="{ notactive: currentPageFormation == totalPagesFormation}">
              <span class="show-more__text">Show 2 more</span>
              <i class="fas fa-angle-down"></i>
            </button>
          </div>




        </div><!--/formation-->


      </div>

     <div class="content__more"><!--content__more-->
       <div class="details details--current"><!--details-->
         <div class="details__item-popup " v-bind:class="{ active: isVisit}">

             <div class="details__item__title">
               <span class="details-text">Current professional status</span>
               <div class="button-container">
                  <button class="edit-info edit-info--details" @click="isVisit = !isVisit"><i class="far fa-times-circle"></i></button>
                  <button class="edit-info edit-info--details" @click="isVisit = !isVisit"><i class="far fa-check-circle"></i></button>
               </div>
             </div>

             <div class="details__item__body">
               <div class="details-row">
                 <div class="details-row__title">Salary base </div>
                 <input class="details-row__description details-row__description--input" type="text"  v-model="sendData.price" placeholder="" />
               </div>
               <div class="details-row">
                 <div class="details-row__title">Salary variables</div>
                 <input class="details-row__description details-row__description--input" type="text"  v-model="sendData.price2" placeholder="" />
               </div>
               <div class="details-row">
                 <div class="details-row__title">Advatages</div>
                 <input class="details-row__description details-row__description--input" type="text"  v-model="sendData.price3" placeholder="" />
               </div>
               <div class="details-row">
                 <div class="details-row__title">Location</div>
                 <input class="details-row__description details-row__description--input" type="text"  v-model="sendData.location" placeholder="" />
               </div>
             </div>

         </div>

         <div class="details__item ">

           <div class="details__item__title">
             <span class="details-text">Current professional status</span>
             <button class="edit-info" @click="isVisit = !isVisit" ><i class="fas fa-pencil-alt"></i></button>
           </div>

           <div class="details__item__body">
             <div class="details-row">
               <div class="details-row__title">Salary base</div>
               <div class="details-row__description">  {{sendData.price}}</div>
             </div>
             <div class="details-row">
               <div class="details-row__title">Salary variables</div>
               <div class="details-row__description">{{sendData.price2}}</div>
             </div>
             <div class="details-row">
               <div class="details-row__title">Advatages</div>
               <div class="details-row__description">{{sendData.price3}}</div>
             </div>
             <div class="details-row">
               <div class="details-row__title">Location</div>
               <div class="details-row__description">{{sendData.location}}</div>
             </div>
           </div>
         </div>
       </div><!--/details-->

       <div class="details details--wished"><!--details-->
         <div class="details__item-popup " v-bind:class="{ active: isVisit2}">

           <div class="details__item__title">
             <span class="details-text">Current professional status</span>
             <div class="button-container">
               <button class="edit-info edit-info--details" @click="isVisit2 = !isVisit2"><i class="far fa-times-circle"></i></button>
               <button class="edit-info edit-info--details" @click="isVisit2 = !isVisit2"><i class="far fa-check-circle"></i></button>
             </div>
           </div>

           <div class="details__item__body">
             <div class="details-row">
               <div class="details-row__title">Salary base </div>
               <input class="details-row__description details-row__description--input" type="text"  v-model="sendData.price4" placeholder="" />
             </div>
             <div class="details-row">
               <div class="details-row__title">Salary variables</div>
               <input class="details-row__description details-row__description--input" type="text"  v-model="sendData.price5" placeholder="" />
             </div>
             <div class="details-row">
               <div class="details-row__title">Advatages</div>
               <input class="details-row__description details-row__description--input" type="text"  v-model="sendData.price6" placeholder="" />
             </div>
             <div class="details-row">
               <div class="details-row__title">Location</div>
               <input class="details-row__description details-row__description--input" type="text"  v-model="sendData.location1" placeholder="" />
             </div>
           </div>

         </div>


         <div class="details__item ">

           <div class="details__item__title">
             <span class="details-text">Wished professional status</span>
             <button class="edit-info" @click="isVisit2 = !isVisit2" ><i class="fas fa-pencil-alt"></i></button>
           </div>

           <div class="details__item__body">
             <div class="details-row">
               <div class="details-row__title">Salary base</div>
               <div class="details-row__description">{{sendData.price4}}</div>
             </div>
             <div class="details-row">
               <div class="details-row__title">Salary variables</div>
               <div class="details-row__description">{{sendData.price5}}</div>
             </div>
             <div class="details-row">
               <div class="details-row__title">Advatages</div>
               <div class="details-row__description">{{sendData.price6}}</div>
             </div>
             <div class="details-row">
               <div class="details-row__title">Location</div>
               <div class="details-row__description">{{sendData.location1}}</div>
             </div>
           </div>
         </div>
       </div><!--/details-->

       <div class="details details--languages"><!--details-->
         <div class="details__item-popup " v-bind:class="{ active: isVisit3}">

           <div class="details__item__title">
             <span class="details-text">Current professional status</span>
             <div class="button-container">
               <button class="edit-info edit-info--details" @click="isVisit3 = !isVisit3"><i class="far fa-times-circle"></i></button>
               <button class="edit-info edit-info--details" @click="isVisit3 = !isVisit3"><i class="far fa-check-circle"></i></button>
             </div>
           </div>

           <div class="details__item__body">
             <div class="details-row">
               <div class="details-row__title">Native </div>
               <input class="details-row__description details-row__description--input" type="text"  v-model="sendData.native" placeholder="" />
             </div>
             <div class="details-row">
               <div class="details-row__title">Intermediate</div>
               <input class="details-row__description details-row__description--input" type="text"  v-model="sendData.intermediate" placeholder="" />
             </div>
           </div>

         </div>


         <div class="details__item ">

           <div class="details__item__title">
             <span class="details-text">Languages</span>
             <button class="edit-info" @click="isVisit3 = !isVisit3" ><i class="fas fa-pencil-alt"></i></button>
           </div>

           <div class="details__item__body">
             <div class="details-row">
               <div class="details-row__title">Native</div>
               <div class="details-row__description">{{sendData.native}}</div>
             </div>
             <div class="details-row">
               <div class="details-row__title">Intermediate</div>
               <div class="details-row__description">{{sendData.intermediate}}</div>
             </div>
           </div>
         </div>
       </div><!--/details-->

     </div><!--/content__more-->

    </div><!--/content-->



</template>

<script>
  export default {
    //el: '#items-container',

    data() {
      return {
        sendData:{
          price:'200',
          price2: '200',
          price3:'',
          price4:'200',
          price5: '200',
          price6:'',
          location:'Paris',
          location1:'Paris',
          native:'French',
          intermediate:'English'

        },
        isVisit: false,
        isVisit2:false,
        isVisit3:false,
        items:[
          {
            image:'../assets/company1.jpg',
            position:'Chief growth officer',
            company: 'High flyers agency',
            location:'Paris area, France',
            date:'Sept 2018 - Aujord\'hui'
          },
          {
            image:'./dist/company2.jpg',
            position:'Chief growth officer',
            company: 'High flyers agency',
            location:'Paris area, France',
            date:'Sept 2017 - Aujord\'hui'
          },
          {
            image:'dist/company1.jpg',
            position:'Chief growth officer',
            company: 'High flyers agency',
            location:'Paris area, France',
            date:'Sept 2018 - Aujord\'hui'
          },
          {
            image:'dist/company2.jpg',
            position:'Chief growth officer',
            company: 'High flyers agency',
            location:'Paris area, France',
            date:'Sept 2017 - Aujord\'hui'
          }
        ],
        itemsFormation:[
          {
            image:'dist/company1.jpg',
            position:'Chief growth officer',
            company: 'High flyers agency',
            location:'Paris area, France',
            date:'Sept 2018 - Aujord\'hui'
          },
          {
            image:'dist/company1.jpg',
            position:'Chief growth officer',
            company: 'High flyers agency',
            location:'Paris area, France',
            date:'Sept 2017 - Aujord\'hui'
          },
          {
            image:'dist/company1.jpg',
            position:'Chief growth officer',
            company: 'High flyers agency',
            location:'Paris area, France',
            date:'Sept 2018 - Aujord\'hui'
          },
          {
            image:'dist/company1.jpg',
            position:'Chief growth officer',
            company: 'High flyers agency',
            location:'Paris area, France',
            date:'Sept 2017 - Aujord\'hui'
          }
        ],
        currentPage: 1,
        currentPageFormation: 1
      }


    },
    computed:{
      toBeShown() {
        return this.items.slice(0, this.currentPage * 2);
      },
      totalPages() {
        return Math.ceil( this.items.length / 2);
      },
      toBeShownFormation() {
        return this.itemsFormation.slice(0, this.currentPageFormation * 2);
      },
      totalPagesFormation() {
        return Math.ceil( this.itemsFormation.length / 2);
      }
    },
    methods: {
   /*   confirm(){
        console.log('DATA PRICE');
        console.log(this.sendData.price);
        alert(this.sendData.price);
      },*/
      nextPage(){
        if(this.currentPage <  this.totalPages) this.currentPage++;
      },
      prevPage(){
        this.currentPage = this.currentPage - 1 || 1;
      },
      nextPageFormation(){
        if(this.currentPageFormation <  this.totalPagesFormation) this.currentPageFormation++;
      },
      prevPageFormation(){
        this.currentPageFormation = this.currentPageFormation - 1 || 1;
      }



    }
  }

</script>


<style lang="sass">


.content
  padding: 0 25px
  box-sizing: border-box
  display: flex
  align-items: flex-start
  justify-content: center
  flex-wrap: wrap
  margin-top: 30px
  &__about
    width: 60%
    @media (max-width: 1024px)
      width: 100%
  &__more
    width: 40%
    @media (max-width: 1024px)
      width: 100%

.experience
  box-sizing: border-box
  margin-right: 20px
  margin-bottom: 20px
  padding: 25px
  box-shadow: 1px 3px 20px -7px rgba(0, 0, 0, 0.48)
  border-radius: 10px
  background: #fff
  @media (max-width: 1024px)
    margin-right: 0
  @media (max-width: 480px)
    padding: 25px 10px
  &__box
  &__title
    padding-bottom: 15px
    display: flex
    align-items: center
    justify-content: space-between
    box-sizing: border-box
    border-bottom: 1px solid #f1ecec
    &__text
      text-transform: uppercase
      font-size: 14px
      font-weight: bold
      color: #140933

    &__years
      font-size: 14px
      font-weight: bold
      color: #00c3dc
.experience__box
  padding: 10px 0
  box-sizing: border-box
  transition: .3s
  height: 100%
.experience-item
  display: flex
  align-items: flex-start
  justify-content: space-between
  box-sizing: border-box
  padding: 25px 0
  border-bottom: 1px solid #f1ecec


  &__date
    font-size: 14px
    color: #939bb3
  &__description
    display: flex
    flex-direction: column
    margin-left: 20px
    @media (max-width: 480px)
      margin-left: 10px
    &__position
      font-size: 18px
      font-weight: bold
      color: #140933
      margin-bottom: 10px
    &__company
      font-size: 14px
      font-weight: bold
      color: #140933
      margin-bottom: 10px
    &__location
      font-size: 14px
      color: #939bb3
  &__img
    width: 50px
    height: 50px
    object-fit: cover
  &__info
    display: flex
    align-items: flex-start
    justify-content: flex-start
.details
  position: relative
  margin-bottom: 10px
  &__item-popup
    position: absolute
    top: 0
    bottom: 0
    left: 0
    right: 0
    width: 100%
    height: 100%
    background: #fff
    padding: 25px
    box-sizing: border-box
    box-shadow: 1px 3px 10px -7px rgba(0, 0, 0, 0.68)
    border-radius: 10px
    transition: .3s
    z-index: -1
    border: 2px solid #c8ccd8
    &.active
      display: block
      transition: .3s
      z-index: 1

  &__item
    box-sizing: border-box
    padding: 25px
    box-shadow: 1px 3px 20px -7px rgba(0, 0, 0, 0.48)
    border-radius: 10px
    background: #fff
    &__title
      padding-bottom: 15px
      display: flex
      align-items: center
      justify-content: space-between
      box-sizing: border-box
      border-bottom: 1px solid #f1ecec

.details-text
  text-transform: uppercase
  font-size: 14px
  font-weight: bold
  color: #140933
.show-more
  text-align: center
  font-size: 12px
  font-weight: bold
  color: #939bb3
  border: none
  margin: 10px auto
  position: relative
  left: 50%
  transform: translate(-50%)
  background: transparent
  outline: none
  &.fas
    padding-left: 5px
  &.notactive
    display: none
  &:hover
    cursor: pointer

.details-row
  display: flex
  align-items: flex-start
  justify-content: flex-start
  margin-top: 15px
  height: 30px

  &__title
    width: 40%
    padding-bottom: 5px
    box-sizing: border-box
    font-size: 14px
    color: #939bb3
  &__description
    width: 60%
    border-bottom: 1px solid #f1ecec
    padding-bottom: 5px
    padding-left: 5px
    box-sizing: border-box
    font-size: 16px
    color: #140933
    font-weight: bold
    height: 30px
    &--input
      padding: 15px 5px
      border: 1px solid #f1ecec
      border-radius: 4px
      background-color: #fafafc

.edit-info
  border: none
  background: transparent
  box-sizing: border-box
  outline: none
  color: #939bb3
  &--details
    height: 30px
    width: 30px
    display: flex
    align-items: center
    justify-content: center
    background-color: #fff
    border-radius: 50%
    box-shadow: 1px 3px 20px -7px rgba(0, 0, 0, 0.48)
    padding: 0
    outline: none
    &:hover
      box-shadow: 1px 3px 20px -7px rgba(0, 0, 0, 0.78)
    &:first-child
      margin-right: 5px
  &:hover
    cursor: pointer

.button-container
  width: 80px
  display: flex
  justify-content: flex-end
.fa-times-circle
  color: #ff708d
  font-size: 20px
.fa-check-circle
  color: #08c5de
  font-size: 20px
.fa-pencil-alt
  font-size: 20px
</style>
