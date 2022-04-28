<template>
  <header>
    <router-link to="/">
      <h1><span>vue</span> movie</h1>
    </router-link>
  </header>
  <main>
    <router-view/>
  </main>
</template>

<style lang="scss">
  * {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
    text-transform: capitalize;
    text-decoration: none;
    font-family: 'Fira Sans', sans-serif;

    &::selection {
      background: transparentize(#42b883, 0.5);
    }
  }
  body {
    background-color: #35495e;
  }
  header {
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 10px 16px;
    background-color: #2c3d4e;
    box-shadow: 0 0 6px rgba(0, 0, 0, .1);
    h1 {
      font-size: 28px;
      color: #fff;
      span {
        color: #42b883;
      }
    }
  }
</style>
