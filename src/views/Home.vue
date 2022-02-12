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
    <form @submit.prevent="searchMovies()" class="search-box">
      <input type="text" placeholder="What are you looking for?" v-model="searchData"/>
      <input type="submit" value="Search">
    </form>

    <div class="movie-list">
      <div class="movies" v-for="movie in movies" :key="movie.imdbID">
        {{movie.Title}}
        </div>
      
    </div>
  </div>
</template>

<script>
  // @ is an alias to /src
  import {ref} from 'vue';
  import env from '@/env.js';

  export default {
    setup(){
      const searchData = ref("");
      const movies = ref([]);

      const searchMovies = () =>{
        if(searchData.value != ""){
          fetch(`http://www.omdbapi.com/?apikey=${env.apikey}&s=${searchData.value}`)
          .then(response => response.json())
          .then(data =>{
            movies.value = data.Search;
            searchData.value = "";

            // console.log(data);
            
          });

        }
      }
      return {

        searchData,
        movies,
        searchMovies
      }

    }
    
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
    object-fit:cover;
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

  .search-box{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 16px;
  }
  input{
    display:block;
    appearance: none;
    border: none;
    outline: none;
    background: none;
  }
  input[type="text"]{
    width: 100%;
    color: #000;;
    background: color #496583;
    font-size: 20px;
    padding: 10px 16px;
    border-radius:8px;
    margin-bottom: 15px;
    transition: 0.4s;
  }
  ::placeholder{
    color: #686464;
  }
  :focused {
    box-shadow: 0 3px 6px rgba(0,0,0,0.2);

  }
  input[type="submit"]{
    width: 100%;
    max-width: 300px;
    background-color: #42b883;
    padding:16px;
    border-radius: 8px;
    color: #fff;
    font-size: 20px;
    text-transform: uppercase;
    transition: 00.4s;
  }
  :active{
    background-color: #3b8070;
  }
</style>
