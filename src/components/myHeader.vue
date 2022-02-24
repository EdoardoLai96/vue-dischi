<template>
  <div class="header d-flex justify-content-between align-items-center px-2">
      <div class="logo_box">
          <img src="../assets/img/spotify-1.svg" alt="">
      </div>
      <select class="form-select ms_w_min ms_h_min" aria-label="Default select example">
        <option selected>Select Genre</option>
        <option v-for="(genre, index) in discGenres" :key="index" :value="genre">{{genre}}</option>
     </select>
  </div>
</template>

<script>
export default {
name: "myHeader",
props:{
    "discGenres" : Array,
},
methods:{
    selectGenere(){
        console.log
    }
}
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