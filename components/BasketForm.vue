<template>
  <form action="#" class="basket__form">
        <h3 class="basket__descr">Оформить заказ</h3>
        <label for="name" class="basket__label">
            <input type="text" class="basket__input" placeholder="Ваше имя">
        </label>
        <label for="name" class="basket__label">
            <input type="text" class="basket__input" placeholder="Телефон">
        </label>
        <label for="name" class="basket__label">
            <input type="text" class="basket__input" placeholder="Адрес">
        </label>
        
        <button class="basket__form-btn">Отправить</button>
        <p class="basket__warning">
            Все поля обязательные. <br> После удачной отправки формы содержимое корзины очищается
        </p>
    </form>
</template>

<script>
export default {

}
</script>

<style lang="sass">
.basket
    &__form
        display: flex
        flex-direction: column
        
    &__label
        margin-bottom: 10px
        &:last-of-type
            margin-bottom: 24px

    &__input
        border: none
        padding: 14px
        width: 100%
        background: #f8f8f8
        border-radius: 8px
    &__form-btn
        padding: 14px
        width: 100%
        color: #fff
        margin-bottom: 32px
        
        font-family: PT Sans
        font-size: 16px
        line-height: 21px
        
        background: #1F1F1F
        border-radius: 8px
    &__warning
        position: relative
        font-family: PT Sans
        font-size: 16px
        font-weight: 400
        line-height: 21px
        padding-left: 20px
        &::before
            position: absolute
            top: 0
            left: 0

            content: '!!'
            font-family: PT Sans
            font-weight: 700
            font-size: 32px
            line-height: 30px

            color: #eb5757
</style>