<template>
  <div class="header d-flex justify-content-between align-items-center px-2">
      <div class="logo_box">
          <img src="../assets/img/spotify-1.svg" alt="">
      </div>
      <select id="tipo_di_genere" @change="selectGenre($event)" class="form-select ms_w_min ms_h_min" aria-label="Default select example">
        <option selected>Seleziona un genere</option>
        <option v-for="(genre, index) in discGenres" :key="index" :value="genre">{{genre}}</option>
     </select>
  </div>
</template>

<script>
export default {
name: "myHeader",
data(){
    return{
        selectedGenre : null,
    }
},
props:{
    "discGenres" : Array,
},
methods:{
    selectGenre(event){
        this.selectedGenre = event.target.value
        console.log(this.selectedGenre)
        this.$emit("selectedGenre", this.selectedGenre)
    }
},


}
</script>

<style lang="scss" scoped>
@import "../assets/style/variables.scss";

    .header{
        height: 100px;
        background-color: $secondaryColor;
        .logo_box{
            height: 100%;
            padding: 10px;
            img{
                height: 100%;
            }
        }
    }



    // MY STYLES
    .ms_w_min{
        width: min-content;
    }
    .ms_h_min{
        height: min-content;
    }
</style>