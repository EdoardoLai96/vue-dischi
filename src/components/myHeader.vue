<template>
  <div class="header">
      <div class="logo_box">
          <img src="../assets/img/spotify-1.svg" alt="">
      </div>
  </div>
</template>

<script>
export default {
name: "myHeader",

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
</style>