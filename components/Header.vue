<template>
    <header class="header">
        <div class="container header__container">
            <a href="#" class="header__logo" aria-label="TestList">TestList</a>
            <button class="header__basket">
                <span class="header__basket-count">3</span>
            </button>
        </div>
    </header>
</template>

<script>
export default {

}
</script>

<style lang="sass">
    $grey: #59606d
    $grey-light: #959dad
.header
    width: 100%
    height: 66px
    padding: 20px 0
    background: #fff
    box-shadow: 0px 4px 16px rgba(0, 0, 0, 0.09)
    border-radius: 0px 0px 8px 8px
    &__container
        display: flex
        justify-content: space-between
        align-items: center
    &__logo
        font-size: 22px
        font-family: 'PT Sans'
        font-weight: 700
        color: $grey
    &__basket
        position: relative
        width: 24px
        height: 26px
        background: url('~assets/basket.svg')
        background-repeat: no-repeat
        background-position: center
        background-size: cover
    
        &-count
            position: absolute
            top: -2px
            right: -3px
            min-width: 12px
            height: 12px
            text-align: center
            font-family: 'PT Sans', sans-serif
            font-weight: 700
            color: #fff
            line-height: 12px
            font-size: 8px
            border-radius: 50%
            background-color: $grey-light

        



</style>