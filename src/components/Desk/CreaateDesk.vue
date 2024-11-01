<script>

export default {
  props: {
    listDesk: Array,
    toggleDesc:Array
  },
  methods: {
    addDesk() {
      if (this.name === ''){
        this.name = 'Новая доска'
      }
      for (let i = 0; i < this.listDesk.length; i++) {
        if (this.listDesk[i].name === this.name) {
          alert('Такая доска уже существует')
          return
        }
      }

      const randomColor = '#' + (Math.random() * 0xFFFFFF << 0).toString(16).padStart(6, '0')
      this.listDesk.push({name: this.name, colorDesck: this.colorDesk})
      this.colorDesk = randomColor
      this.name = ''
    },
    AddCard(index) {
      this.$emit('update:toggle-desc', this.listDesk[index])

    },
    DelDesk(index) {
      this.listDesk.splice(index, 1)
      this.$emit('update:toggle-desc', null)
    }
  },
  data() {
    return {
      name: '',
      colorDesk: '#' + (Math.random() * 0xFFFFFF << 0).toString(16).padStart(6, '0'),
    }
  }
}

</script>

<template>
  <div class="Desk flex flex-col justify-start items-center gap-3.5 p-2 ">
    <!--    Header-->
    <div class="flex w-full flex-row justify-center items-center rounded-xl overflow-hidden">
      <input v-model="colorDesk" type="color" class="Color" >
      <input v-model="name" class="outline-0 border-0 text-[10px] w-full h-[40px] shadow p-5" type="text" placeholder="Название доски" @keydown.enter="addDesk">
      <button class="cursor-pointer w-[50px] h-[100%] bg-white active:bg-amber-200" @click="addDesk">+</button>
    </div>
    <!--  Center  -->
    <div class="DescCard h-[430px] w-[100%] overflow-y-auto gap-3.5">



      <div v-for="(item, index) in listDesk" class="Title mb-1 w-full h-[50px] flex flex-row justify-between items-center cursor-pointer">

        <div  @click="AddCard(index)" class="Tit w-full h-[50px] flex justify-between items-center cursor-pointer">
          <div class="w-[10%] h-full flex justify-center items-center text-xl font-extrabold" :style="`background:${item.colorDesck}`">#</div>
          <div class="w-[90%] rounded-xl h-full flex justify-between items-center p-3">{{ item.name }}
            <div @click="DelDesk(index)" class="Close p-1 rounded-3xl cursor-pointer select-none">❌</div>
          </div>
        </div>

      </div>

    </div>

  </div>

</template>

<style scoped>
*{
  transition: 0.1s;
  //border: 1px solid black;

}
.Close{
  display: none;
}
.Title{
  border-radius: 10px;
  overflow: hidden;
  background: white;
}
.Title:hover .Close{
  display: flex;
  opacity: 1;
}
.Title:hover{

  opacity: 0.7;
}

.Desk{
  width: 100%;
  height: 100%;
  border-radius: 20px;
}
.DescCard::-webkit-scrollbar {
  width: 5px;

}
.DescCard::-webkit-scrollbar-track {
  background: transparent;
}
.DescCard::-webkit-scrollbar-thumb {
  background: v-bind(colorDesk);
  border-radius: 10px;

}
.Color{
  width: 60px;
  height: 100%;
  background: transparent;
}
input[type="color"]::-webkit-color-swatch-wrapper {
  padding: 0;
}
input[type="color"]::-webkit-color-swatch {
  border: none;
}
/* firefox */
input[type=color]::-moz-focus-inner {
  border: none;
  padding: 0;
}
input[type=color]::-moz-color-swatch {
  border: none;
  height: 140px;
}

</style>