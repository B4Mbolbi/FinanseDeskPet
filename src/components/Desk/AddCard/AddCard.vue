<script>

import Emoji from '@/components/Desk/AddCard/Emoji.vue'
import InputText from '@/components/UI/InputText.vue'

export default {
  components: {InputText, Emoji},
  props:{
    toggleClose: Function,
    arrInfo: {
      type: Array,
      default: () => []
    },
    color: String
  },
  methods: {
    AddToArray(){

      if (Object.values(this.selfArrInfo).every(value => value !== '')) {
        this.arrInfo.push({...this.selfArrInfo});
        this.selfArrInfo = {
          title: '',
          date: '',
          sum: '',
          teg: this.selfArrInfo.teg
        };

      } else {
            this.titleChanged = true,
            this.dateChanged = true,
            this.sumChanged = true,
            this.tegChanged = true
      }
    },
    addEmojiToArr(emoji) {
      this.selfArrInfo.teg = emoji
    }
  },
  data() {
    return {
      selfArrInfo:{
        title: '',
        date: '',
        sum: '',
        teg: '🍎'
      },
      titleChanged: false,
      dateChanged: false,
      sumChanged: false,
      tegChanged: false
    }
  }
}
</script>

<template>

  <div class="DeskAdd">
        <div class="Wrapper">
          <InputText v-model="selfArrInfo.title" placeholder="Название" :color="color"></InputText>
    <!--      <input type="text" placeholder="Название" v-model="selfArrInfo.title" @input="titleChanged = true">-->
          <div v-if="selfArrInfo.title === '' && titleChanged" class="Error">❌</div>
        </div>

        <div class="Wrapper">
          <InputText v-model="selfArrInfo.date" placeholder="Дата" type="date" :color="color"></InputText>
          <div v-if="selfArrInfo.date === '' && titleChanged" class="Error">❌</div>
        </div>

      <div class="Wrapper">
        <InputText v-model="selfArrInfo.sum" placeholder="Сумма" type="number" :color="color"></InputText>
        <div v-if="selfArrInfo.sum === '' && titleChanged" class="Error">❌</div>
        <Emoji @emoji-selected="addEmojiToArr"></Emoji>
      </div>
      <button @click="AddToArray" class="addCard">+</button>
  </div>


</template>

<style scoped>

.DeskAdd{
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  position: relative;
  height: 70%;
  width: 100%;
  border-radius: 20px;
  padding: 10px;
  //background: #F7F7F7;
}
.Wrapper{
  width: 100%;
  height: 70px;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  gap: 5px;

}
.Error{
  font-size: 12px;
  padding: 10px;
  width: 20%;
  height: 50px;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: 0.5s;
}
.addCard{
  font-family: "Courier New", Courier, monospace;
  font-weight: bold;
  font-size: 20px;
  border-radius: 20px;
  padding: 5px;
  outline: none;
  border: none;
  transition: 0.1s;
  width: 70px;
  background: #F7F7F7;
}

button{
  transition: 0.5s;
}
button:hover{
  transform: scale(1.1);
  //background: v-bind(color);
}
</style>