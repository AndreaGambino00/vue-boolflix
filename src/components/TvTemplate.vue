<template>
  <div class="card">
    <div class="content">
      <li class="card-img">
        <img :src="imgPath + imgWidth + item.poster_path" alt="">
      </li>
      <li class="card-info">
        <div class="title">{{ 'Titolo: ' + item.title }}</div>
        <div class="original-title">{{ 'Titolo Originale: ' + item.original_title }}</div>
       
        <div class="rating">
          <fa v-for='(star, index) in Math.ceil(voteRange(item.vote_average, 0, 10 ,1, 5))' :key="index" icon="star" />  
        </div>
      </li>
    </div>
  </div>  
</template>

<script>

export default {
    name: 'MovieTemplate',
    props: ['item'],
    components: {
      
    },
    data() {
      return {
        imgPath: 'https://image.tmdb.org/t/p/',
        imgWidth: 'w342'
      }
    },
    methods: {
      getLang(lang) {
        if (lang == 'en')
          return 'gb';
        return lang
      },
      voteRange(number, inMin, inMax, outMin, outMax) {  
        return (number - inMin) * (outMax - outMin) / (inMax - inMin) + outMin;
      }
    }
}
</script>

<style scoped lang="scss">
   
  .card {
    
  
    height: 350px;
    margin:3px;
  
    &:hover .content {
      transform: rotateY(180deg)
    }
    .content {
      position: absolute;
      width: 20%;
      height: 40%;
      transition: transform 1s;
      transform-style: preserve-3d;
      backface-visibility: hidden;
      -moz-backface-visibility: hidden;
        
      .card-img {
        position: absolute;
        list-style: none;
        width: 90%;
        height: 100%;
        backface-visibility: hidden;
        -moz-backface-visibility: hidden;
        z-index: 1 ;
  
        img {
          width: 83%;
          height: 100%;
         
        }
      }
        
      .card-info {
        position: absolute;
        width: 67%;
        height: 93%;
        padding: 10px;
        background-color: black;
        color: white;
        border-radius: 5px;
        transform: rotateY(180deg);
      }
    }
  }
</style>