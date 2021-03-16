<template>
  <aside class="cart" :data-category="this.$props.card.category">
      <div class="rating cart__rating">
          <div class="rating-img cart__rating-img">
              <svg width="20" height="20" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path fill-rule="evenodd" clip-rule="evenodd" d="M10 3.125C10.2379 3.125 10.4552 3.26005 10.5605 3.47336L12.3464 7.09154L16.3404 7.67532C16.5758 7.70972 16.7712 7.87473 16.8445 8.10098C16.9179 8.32723 16.8565 8.57552 16.6861 8.74147L13.7966 11.5559L14.4785 15.5318C14.5187 15.7663 14.4223 16.0033 14.2299 16.1432C14.0374 16.283 13.7822 16.3014 13.5716 16.1907L10 14.3124L6.42843 16.1907C6.21785 16.3014 5.96267 16.283 5.77018 16.1432C5.5777 16.0033 5.48129 15.7663 5.52151 15.5318L6.20344 11.5559L3.31394 8.74147C3.14355 8.57552 3.08213 8.32723 3.15549 8.10098C3.22885 7.87473 3.42428 7.70972 3.65963 7.67532L7.6536 7.09154L9.43958 3.47336C9.54487 3.26005 9.76213 3.125 10 3.125ZM10 5.16203L8.62921 7.93914C8.53825 8.12342 8.36251 8.25121 8.15916 8.28093L5.09278 8.72913L7.3111 10.8898C7.45852 11.0334 7.52581 11.2403 7.49102 11.4432L6.96763 14.4948L9.70911 13.0531C9.89122 12.9573 10.1088 12.9573 10.2909 13.0531L13.0324 14.4948L12.509 11.4432C12.4742 11.2403 12.5415 11.0334 12.6889 10.8898L14.9073 8.72913L11.8409 8.28093C11.6375 8.25121 11.4618 8.12342 11.3708 7.93914L10 5.16203Z" fill="#F2C94C"/>
                <path d="M6.5 11L4 8H10H16L13.5 11V14.5L13 15.5L10 14L9 14.5L6.5 15.5V14.5V11Z" fill="#F2C94C"/>
            </svg>
          </div>
          <span class="rating-descr cart__rating-descr">{{ this.$props.card.rating }}</span>
      </div>
      <button class="cart__add" type="button"></button>
          <!--  -->
      <div class="cart__img">
          <img :src="`https://frontend-test.idaproject.com${this.$props.card.photo}`" 
          loading="lazy" 
          :alt="this.$props.card.name">
      </div>
      <h3 class="cart__title">{{ this.$props.card.name }}</h3>
      <span class="cart__price">{{ this.$props.card.price }} ₽</span>
  </aside>
</template>

<script>
export default {
    
    props: ['card'],
    
    created() {
        // console.log(this.$props);
        // console.log(this.$props.card);
        
    }
    

}
</script>

<style lang="sass">

$gold: #f2c94c


.rating
    display: flex
    align-items: center
.rating-img
    width: 20px
    height: 20px
.rating-descr
    font-size: 12px
    font-weight: 700
    line-height: 20px
    color: $gold
    
    
.cart
    position: relative
    display: flex
    flex-direction: column
    padding: 17px 16px
    margin-bottom: 16px
    width: 264px
    
    background: #FFFFFF
    box-shadow: 0px 4px 16px rgba(0, 0, 0, 0.05)
    border-radius: 8px

    &__img
        margin: 0 auto
        margin-bottom: 16px
        max-width: 143px
        max-height: 180px
    &__rating
        position: absolute
        top: 17px
        left: 16px
        
    &__rating-img
        
        margin-right: 3px
        
    &__add
        position: absolute
        top: 17px
        right: 18px
        width: 13px
        height: 14px
        background: url('~assets/basket.svg')
        background-repeat: no-repeat
        background-position: center
        background-size: cover
        opacity: 0.8
        &.active
            opacity: 1
        
    &__title
        margin-bottom: 6px

        font-size: 14px
        font-weight: 400
        color: #59606d
    &__price
        font-size: 14px
        font-weight: 700
        color: #1f1f1f
    
</style>