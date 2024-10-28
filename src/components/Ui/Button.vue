<script>
export default {
  props: {
    img: {
      default:'',
      type: String
    },
    title:{
      default: 'Title None',
      type: String
    }
  }
}
</script>

<template>

  <button class="flex-row gap-3.5 overflow-hidden flex justify-start items-center hover:bg-blue-400 h-10 w-full p-2 outline-0 rounded">
    <div class="w-[30px]">
      <img class="w-[100%] h-full" :src="this.img" alt="">
    </div>

    <div>{{ this.title }}</div>
  </button>
  
  
</template>

<style scoped>
button {
  box-shadow: 0px 0px 1px lightskyblue;
}
button:hover {
  div {
    //background: blue;
    padding: 5px;
    //border-radius: 20px;
    opacity: 0.5;
    transition: 0.2s;
  }

  img {
    transition: 0.1s;
    transform: scale(1.3);
  }
}
button:active {
  div{
    color: black;
  }
  img {
    transform: scale(1.5);
  }
}

</style>