<template>
<link href="https://fonts.googleapis.com/css2?family=Russo+One&display=swap" rel="stylesheet">
<link href="https://fonts.googleapis.com/css2?family=Teko:wght@400;500&display=swap" rel="stylesheet">
  <div class="movie-detail">
    <h2>{{movie.Title}}</h2>
    <p>{{movie.Year}} |  {{movie.Country}}</p>
    <img :src="movie.Poster" alt="Movie Poster" class="featured-img" />
    <p> {{movie.Plot}} </p>
   </div>

</template>

<script>
import {ref, onBeforeMount} from 'vue';
import { useRoute } from 'vue-router';
import env from '@/env.js';

export default{
    setup(){
      const movie = ref({});
      const route = useRoute();

      onBeforeMount(()=>{
      fetch(`http://www.omdbapi.com/?apikey=${env.apikey}&i=${route.params.id}&plot=full`)
        .then(response => response.json())
        .then(data => {
          movie.value=data;
        });
      });

      return{
        movie
      }
    }
}
</script>

<style lang="scss">
   .movie-detail{
     padding:16px;

     h2{
       color: #FFF;
       font-size:28px;
       font-weight: 600;
       margin-bottom:16px;
      font-family: 'Russo One', sans-serif;

     }
     .featured-img{
       display:block;
       max-width:200px;
       margin-bottom:16px;
        display: block;
    margin: 0 auto;
     }
     p{
       color:#FFF;
       font-size:18px;
       line-height:1.4;
        font-family: 'Russo One', sans-serif;

     }
   }

</style>
