<template>
  <header>
    <router-link to="/">
      <h1><span>Vue</span>Movies</h1>
    </router-link>
  </header>

  <main>
    <router-view/>
  </main>

</template>

<style>

  * {
    box-sizing: border-box;
    margin:0;
    padding:0;
    font-family: 'Fira Sans', sans-serif;
  }

  ::selection {
    /* color: red; */
    background: #42b883
  }
  body {
    background: color #35495e;
  }
  a {
    text-decoration: none;
  }
  header {
    display : flex;
    align-items : center;
    justify-content : center;
    padding: 10px 16px;
    background-color: #2c3d4a;
    box-shadow: 0px 0px 6px rgba(0, 0, 0,0.1);
  }
  h1 {
    color: #fff;
    font-size: 28px;

  }
  span {
    color: #42b883;
  }

</style>
