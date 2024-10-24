<script setup>

</script>

<template>

  <div class="Wrapper flex flex-row justify-center items-center gap-3.5">
    <div class="Photo rounded-full">
      <img src="https://cdn.icon-icons.com/icons2/4222/PNG/512/leonardo_dicaprio_avatar_icon_263217.png">
    </div>
    <div class="Info flex flex-col justify-center">
      <h1 class="text-amber-700 font-bold text-1xl">Raxmed</h1>
    </div>
  </div>

</template>

<style scoped>
.Wrapper{
  width: 100%;
}
.Photo{
  width: 70px;
  border-radius: 50%;
  overflow:hidden;
  background: peru;
  margin-left: 10px;
}
.Photo img{
  transform: scale(1.2);
}
.Info{
  width: 50%;
  height: 100%;

}
.Info h1{
  color: black;
}




</style>