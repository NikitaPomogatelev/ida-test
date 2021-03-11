<template>
  <section class="catalog">
      <div class="container">
          <div class="catalog-top">
          <h2 class="catalog__title">Каталог</h2>
            <div class="catalog__select">
                <p class="catalog__select-title">Сортировать по:</p>

            </div>
          </div>
          <div class="catalog__inner">
              <aside class="catalog__sidebar">
                  <ul class="catalog__sidebar-list">
                      <li class="catalog__sidebar-item">
                          <button class="catalog__sidebar-btn catalog__sidebar-btn--current" type="button">Рюкзаки</button>
                      </li>
                      <li class="catalog__sidebar-item">
                          <button class="catalog__sidebar-btn" type="button">Футболки</button>
                      </li>
                      <li class="catalog__sidebar-item">
                          <button class="catalog__sidebar-btn" type="button">Рубашки</button>
                      </li>
                  </ul>
              </aside>
              <ul class="catalog__list">
                  <li class="catalog__item"></li>
                  <li class="catalog__item"></li>
              </ul>
          </div>
      </div>
  </section>
</template>

<script>
export default {

}
</script>

<style lang="sass">
 $black: #1f1f1f
 $grey-light: #959dad
 $gray: #59606d
.catalog
    margin-top: 30px
    &__title
        margin-bottom: 24px
        font-size: 32px
        font-family: 'PT Sans', sans-serif
        font-weight: 700
        color: $black
    &__inner
        display: flex
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
        
        

</style>