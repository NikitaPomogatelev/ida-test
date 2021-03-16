<template>
    <div class="basket">
        <div class="basket-overlay">
            <div class="basket__wrapper">
                <div class="basket__top">
                    <h2 class="basket__title">Корзина</h2>
                    <button class="basket__close" aria-label="Закрыть корзину"></button>
                </div>
                    <span class="basket__descr">Товары в корзине</span>
                <ul class="basket__list">
                    <li class="basket__item">
                        <div class="basket__item-img">
                            <img src="~static/basket-img.png" loading="lazy" alt="Картинка товара"> 
                        </div>
                        <div class="basket__item-right">
                            <h3 class="basket__item-title">Рюкзак Louis Vuitton Discovery</h3>
                            <strong class="basket__item-price">150 000 ₽</strong>
                            <div class="rating">
                                <div class="rating-img">
                                    <svg width="20" height="20" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
                                        <path fill-rule="evenodd" clip-rule="evenodd" d="M10 3.125C10.2379 3.125 10.4552 3.26005 10.5605 3.47336L12.3464 7.09154L16.3404 7.67532C16.5758 7.70972 16.7712 7.87473 16.8445 8.10098C16.9179 8.32723 16.8565 8.57552 16.6861 8.74147L13.7966 11.5559L14.4785 15.5318C14.5187 15.7663 14.4223 16.0033 14.2299 16.1432C14.0374 16.283 13.7822 16.3014 13.5716 16.1907L10 14.3124L6.42843 16.1907C6.21785 16.3014 5.96267 16.283 5.77018 16.1432C5.5777 16.0033 5.48129 15.7663 5.52151 15.5318L6.20344 11.5559L3.31394 8.74147C3.14355 8.57552 3.08213 8.32723 3.15549 8.10098C3.22885 7.87473 3.42428 7.70972 3.65963 7.67532L7.6536 7.09154L9.43958 3.47336C9.54487 3.26005 9.76213 3.125 10 3.125ZM10 5.16203L8.62921 7.93914C8.53825 8.12342 8.36251 8.25121 8.15916 8.28093L5.09278 8.72913L7.3111 10.8898C7.45852 11.0334 7.52581 11.2403 7.49102 11.4432L6.96763 14.4948L9.70911 13.0531C9.89122 12.9573 10.1088 12.9573 10.2909 13.0531L13.0324 14.4948L12.509 11.4432C12.4742 11.2403 12.5415 11.0334 12.6889 10.8898L14.9073 8.72913L11.8409 8.28093C11.6375 8.25121 11.4618 8.12342 11.3708 7.93914L10 5.16203Z" fill="#F2C94C"/>
                                        <path d="M6.5 11L4 8H10H16L13.5 11V14.5L13 15.5L10 14L9 14.5L6.5 15.5V14.5V11Z" fill="#F2C94C"/>
                                    </svg>
                                </div>
                                <span class="rating-descr">4.5</span>
                            </div>
                            <button class="basket__btn" type="button"></button>
                        </div>
                    </li>
                    
                </ul>
                <BasketForm />
            </div>

        </div>
    </div>
</template>

<script>
export default {

}
</script>

<style lang="sass">
.basket
    position: fixed
    top: 0
    bottom: 0
    left: 0
    right: 0
    width: 100%
    height: 100vh
    z-index: 97
    display: none
    
    &-overlay
        position: absolute
        top: 0
          
        left: 0
        width: 100%
        height: 100%
        background: rgba(#fff , 0.8)
        


    &__wrapper
        position: absolute
        top: 0
        right: 0
        width: 460px
        height: 100vh
        padding: 52px 48px

        font-family: 'PT Sans'
        background: #fff  

        box-shadow: -4px 0px 16px rgba(0, 0, 0, 0.05)
        border-radius: 8px 0px 0px 8px
        
        z-index: 99
        
    &__title
        
        font-size: 32px
        margin-bottom: 24px
    &__descr
        display: block
        margin-bottom: 16px

        font-size: 18px
        color: #59606d

        
    &__top
        display: flex
        justify-content: space-between
        align-items: center
    &__close
        width: 14px
        height: 14px
        background: url('~assets/close.svg')
        background-repeat: no-repeat
        background-position: center
        background-size: cover
    &__list
        margin-bottom: 30px
    &__item
        position: relative
        display: flex
        
        padding: 12px 15px
        box-shadow: 0px 0px 16px rgba(0, 0, 0, 0.05)
        &:not(:last-of-type)
            margin-bottom: 16px
            
    &__item-img
        margin-right: 34px
    &__item-title
        max-width: 135px
        font-size: 14px
        color: #59606d
        margin-bottom: 6px
    &__item-price
        display: block
        margin-bottom: 16px

        font-size: 14px
        font-weight: 700
        color: #1f1f1f

    
    
    &__btn
        position: absolute
        top: 50%
        right: 20px
        width: 20px
        height: 22px
        transform: translateY(-50%)
        background: url('~static/trash.svg')
        background-repeat: no-repeat
        background-position: center
        background-size: cover
        opacity: 0.6
        transition: opacity .3s ease, color .3s ease
        &:hover
            opacity: 1
            color: #1f1f1f
        &.active
            opacity: 1
            color: #1f1f1f
    
    
            
            
</style>