<template>
  <div class="home">
    <div class="feature-card">
      <router-link to="/movie/tt040951">
       <img src="https://lumiere-a.akamaihd.net/v1/images/p_aladdin2019_17638_d53b09e6.jpeg" alt="Naruto" class="featured-img" />
      <div class="detail">
        <h3>Naruto</h3>
        <p>
          Placeholder.com is a free image placeholder service for web designers, serving billions of images per year.
        </p>
      </div>
      </router-link>
    </div>
  </div>
</template>

<script>
  // @ is an alias to /src

  export default {
    
  }
</script>

<style scoped>
 
  .feature-card{
    position: relative;

  }
  .featured-img{
    display: block;
    width: 100%;
    height: 300px;
    object-fit: cover;
    position: relative;
    z-index: 0;
  }

  .detail{
    position: absolute;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: rgba(0, 0, 0, 0.6);
    padding: 16px;
    z-index: 1;
  }
  h3{
    color:#fff;
    margin-bottom:16px;
  }
  p{
    color:#fff;
  }
</style>
