<template>
      <div class="col">
        <div class="card  border-0  ms_bg_secondary h-100 " style="width: 15rem;">
            <img :src="disc.poster" class="card-img-top h-100 p-3" alt="...">
            <h5 class="card-title text-center text-light fs-7">{{disc.title}}</h5>
            <p class="card-text text-center mb-0 text-secondary">{{disc.author}}</p>
            <p class="card-text text-center text-secondary mb-1">{{disc.year}}</p>
        </div>
    </div>
</template>

<script>
export default {
name: "myCard",
props: {
    "disc" : Object,
}

}
</script>

<style scoped lang="scss">
@import "../../assets/style/variables.scss";
main{
  height: 100%;
}

/* MY STYLES  */
.ms_bg_primary{
background-color: $primaryColor;
}
.ms_bg_secondary{
background-color: $secondaryColor;
}

.ms_min-w-{
    min-width: 200px;
}

</style>