<template>
<main class="ms_bg_primary">
<div class="container py-5 d-flex justify-content-center">
    <div class="row gx-3 gy-3 flex-wrap h-100 flex-center disc_box">
      <myCard :disc="disc"  v-for="(disc, index) in filteredByGenre" :key="index" />
    </div>
</div>
</main>
</template>

<script>
  import myCard from "./partials/myCard.vue"
 const axios = require('axios');



export default {
name: "myMain",
data(){
  return{
    discCollection : [],
    discGenres: [],
  }
},
props:{
  selectedGenre: String
},
computed:{
filteredByGenre(){
  if(this.selectedGenre == ""){
    return this.discCollection
  }else{
    return this.discCollection.filter(item => {
      return item.genre == this.selectedGenre;
    })

  }

}
},
components:{
  myCard
},
methods:{
  getDiscs(){
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
  .then((response) => {
    // handle success
    this.discCollection = response.data.response;
    console.log(response.data.response)


    this.discCollection.forEach(element => {
      if(!this.discGenres.includes(element.genre)){
        this.discGenres.push(element.genre)
      }
    });

    console.log(this.discGenres)

    this.filterGenres();
  })
  },
  filterGenres(){
    this.$emit('exportGenres', this.discGenres)
  },


},
mounted(){
  this.getDiscs()
}

}
</script>







<style scoped lang = "scss">
@import "../assets/style/variables.scss";
main{
  min-height: calc(100vh - 100px);
}

/* MY STYLES  */
.ms_bg_primary{
background-color: $primaryColor;
}
.ms_bg_secondary{
background-color: $secondaryColor;
}
</style>