<template>
  
 
    <Nuxt />
  
</template>

<style lang="scss">

/* Шрфиты */
@font-face {
  font-family: 'PT Sans';
  font-style: normal;
  font-weight: 400;
  font-display: swap;
  src: url('~assets/fonts/PT-sans/PTSans-Regular.woff2') format('woff2');
}

@font-face {
  font-family: 'PT Sans';
  font-style: normal;
  font-weight: 700;
  font-display: swap;
  src: url('~assets/fonts/PT-sans/PTSans-Bold.woff2') format('woff2');
}

/* Глобальные настройки */
html {
  font-family:

    'PT Sans',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}

button {
    padding: 0;
    background-color: transparent;
    cursor: pointer;
    border: none;
}

a {
    text-decoration: none;
    color: inherit;
}

ul, li {
    margin: 0;
    padding: 0;
    list-style: none;
}

h1, h2, h3 {
    margin: 0;
}
p {
    margin: 0;
}

</style>
