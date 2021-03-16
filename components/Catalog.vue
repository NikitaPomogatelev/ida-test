<template>
  <section class="catalog">
      <div class="container catalog__container">
        <div class="catalog-top">
            <h2 class="catalog__title">Каталог</h2>
            <div class="catalog__custom-select custom-select" >
                <div class="custom-select__top">
                    <p class="custom-select__title">Сортировать по:</p>
                    <div class="custom-select__selected" @click="selectOpen = !selectOpen" ref="selectedText">цене</div>
                </div>
                <div class="custom-select__dropdown">
                    <ul class="custom-select__list" :class=" {active: selectOpen}">
                        <li class="custom-select__item" @click="sortItems('price')">По цене</li>
                        <li class="custom-select__item" @click="sortItems('popular')">По популярности</li>
                    </ul>
                </div>
            </div>
        </div>
          <div class="catalog__inner">
              <aside class="catalog__sidebar">
                  <ul class="catalog__sidebar-list">
                      <li class="catalog__sidebar-item" 
                            v-for="category in categories"
                          :key="category.id">
                          <button class="catalog__sidebar-btn"
                                @click="sortCategory(category.id)" 
                                type="button"
                          >
                          {{category.name}}
                          </button>
                          </li>
                  </ul>
              </aside>
              <div class="catalog__list" v-if="!temp">  
                    <Cart  v-for="card in sortArr" :key="card.id" :card="card"/>     
              </div>
              <div class="catalog__list" v-else>            
                    <Cart  v-for="card in cards" :key="card.id" :card="card"/>
              </div>
          </div>
      </div>
  </section>
</template>

<script>
import Cart from './Cart.vue'

export default {
    components: {
            Cart,
        },
        created() {
        const getData = async (url, callback) => {
            await fetch(url)
                .then((res) => {
                    if(!res.ok) {
                        throw new Error(`Ошибка по адресу ${url}, статус ошибки: ${res.status}`);
                    }
                        return res.json();
                })
                .then(callback)
                .catch((err) => {
                    console.log(err);
                })        
        }

    // this.cards = data
    
    getData('https://frontend-test.idaproject.com/api/product', data => {
        this.cards = data;
        // console.log(this.cards);
    });
    getData('https://frontend-test.idaproject.com/api/product-category', data => {
        this.categories = data;
        // console.log(this.cards);
    });
  },
  data: () => {
        return {
            cards: [],
            categories: [],
            selectOpen: false,
            sortArr: [],
            temp: true
        };
    },

    methods: {
        sortItems(e) {
            if(e === 'price') {
                this.cards = this.cards.sort((a,b) => b.price - a.price)
                this.sortArr = this.sortArr.sort((a,b) => b.price - a.price)
                this.$refs.selectedText.textContent = 'цене'
            } 

            else if(e === 'popular') {
                console.log(345345);
                this.cards = this.cards.sort((a,b) => b.rating - a.rating)
                this.sortArr = this.sortArr.sort((a,b) => b.rating - a.rating)
                this.$refs.selectedText.textContent = 'популярности' 
            } 
            
            this.selectOpen = !this.selectOpen
        },
        sortCategory(event) {
            this.sortArr = this.sortArr.splice(0, this.sortArr.length);
            this.sortArr = this.cards;
    
            console.log(1, this.sortArr);
            this.sortArr = this.sortArr.filter( e => {
                return e.category === event;
            });
            console.log(2, this.sortArr);
            this.temp = false;

            
            
        }
    },
    computed: {
        
    },
    
    
  
}


</script>


<style lang="sass">
    $black: #1f1f1f
    $grey-light: #959dad
    $gray: #59606d


.catalog
    margin-top: 30px
    min-height: 1000px
    &-top
        display: flex
        justify-content: space-between
        
        
    &__title
        margin-bottom: 24px
        font-size: 32px
        font-family: 'PT Sans', sans-serif
        font-weight: 700
        color: $black
    &__inner
        display: flex
    &__sidebar
        min-width: 161px
    &__sidebar-item:not(:last-of-type)
        margin-bottom: 16px
        
    &__sidebar-btn
        font-family: 'PT Sans', sans-serif
        font-weight: 400
        font-size: 16px
        color: $grey-light
        transition: color .3s ease
        outline: none
        &:hover
            color: $gray
            
    &__sidebar-btn--current
        text-decoration: underline
        color: $black
    &__list
        display: flex
        flex-wrap: wrap
        justify-content: space-between
        
        
.custom-select
        
    &__top
        position: relative
        display: flex
        &::after
            content: ''
            position: absolute
            top: 45%
            right: -13px
            
            border: 4px solid transparent
            border-top: 5px solid $gray
    &__title
        margin-right: 6px
        font-weight: 400
        font-size: 16px
        line-height: 21px
        color: $black
    &__selected
        color: $gray
        cursor: pointer
    &__dropdown
        position: relative
    &__list
        position: absolute
        top: 0
        left: 0
        
        background: #fff
        box-shadow: 0px 4px 16px rgba(0, 0, 0, 0.05)
        border-radius: 8px
        z-index: 999

        height: 0
        overflow: hidden
        
        &.active
            height: 100%
            overflow: inherit
    &__item
        width: 160px
        padding: 10px 14px
        font-weight: 400
        
        font-size: 14px
        line-height: 18px
        background: #fff
        transition: background .4s ease
        cursor: pointer
        &:hover
            background: #f8f8f8
            

</style>