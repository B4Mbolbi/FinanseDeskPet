<script>
export default {
  props:{
    title: String,
    date: String,
    teg: String,
    sum: String,
    status: String,
    color: String,
  },
  methods: {
    deleteCard() {
      this.$emit('delete-card');
    }
  }
}
</script>


<template>

    <div class="WrapperR">
      <div class="absolute left-0 top-0 z-10 text-white w-full flex justify-between items-center  pl-2.5">
        <div># {{title}}</div>
        <button @click="deleteCard" class="w-[20px] h-[100%] text-[10px] rounded-3xl cursor-pointer hover:bg-amber-700">❌</button>
      </div>
<!--💰 📅 ❌ ⭕️-->

      <div class="flex justify-start flex-col text-white items-center w-full h-[50%] ">
        <ul class="w-full h-full flex flex-col justify-start items-center">
          <li class="w-full h-full flex flex-row justify-start items-center mb-1">
            <div class="w-2/4 h-full flex justify-center items-center text-[11px]">Сумма 💰</div>
            <div class="text-[9px] w-3/4 h-full flex justify-start pl-2.5 items-center bg-black rounded-3xl">{{sum}} RUB</div>
          </li>
          <li class="w-full h-full flex flex-row justify-start items-center">
            <div class="w-2/4 h-full flex justify-center items-center text-[11px]">Дата 📅</div>
            <div class="text-[9px] w-3/4 h-full flex justify-start pl-2.5 items-center bg-black rounded-3xl">{{date}}</div>
          </li>
        </ul>
      </div>
      <div class="BgEmo absolute">
        <div v-for="i in 15" :key="i" class="Emojies w-[90px] h-[50px]">
          <div class="w-[100%] h-[50%] flex justify-between items-center">
            <p class="text-3xl">{{teg}}</p>
            <p></p>
          </div>
          <div class="w-[100%] h-[50%]  flex justify-center items-center">
            <p>{{teg}}</p>
          </div>
        </div>
      </div>
    </div>


</template>
<style scoped>
*{
  font-weight: bold;
  font-family: "Arial Black", Gadget, sans-serif;
}
*:hover{
  cursor: pointer;
  border: 1px solid peru;
  //font-size: 30px;
}
.WrapperR{
  width: 40%;
  height: 120px;
  position: relative;
  z-index: 10;
  display: flex;
  justify-content: center;
  align-items: center;
  overflow: hidden;
  border-radius: 10px;
  background: peru;
}
.WrapperR:hover{



}

@keyframes bgAnimate {
  0%{
    transform: scale(1.2);
  }
  50%{
    transform: scale(1.1);
  }
  100%{
    transform: scale(1.2);
  }
}

.BgEmo{
  display: flex;
  flex-wrap: wrap;
  width: 500px;
  height: 150px;
  background: transparent;
  animation: bgAnimate 5s ease infinite;
  z-index: 0;
}

.Emojies{
  font-size: 15px;
  opacity: .3;
}

</style>

