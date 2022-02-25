<template>
  <div class="header d-flex justify-content-between align-items-center px-2">
      <div class="logo_box">
          <img src="../assets/img/spotify-1.svg" alt="">
      </div>
      <select v-model="selectedGenre" id="tipo_di_genere" @change="selectGenre()" class="form-select ms_w_min ms_h_min" aria-label="Default select example">
        <option value="">Seleziona un genere</option>
        <option v-for="(genre, index) in discGenres" :key="index" :value="genre">{{genre}}</option>
     </select>
  </div>
</template>

<script>
export default {
name: "myHeader",
data(){
    return{
        selectedGenre : "",
    }
},
props:{
    "discGenres" : Array,
},
methods:{
    selectGenre(){
        // this.selectedGenre = event.target.value
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