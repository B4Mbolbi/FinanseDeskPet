<template>
  <div class="flex flex-col-reverse relative">
    <div @click="openEmojiPicker" class="w-[50px] h-[50px]
     flex justify-center items-center cursor-pointer text-[25px] rounded-3xl select-none">
      {{ emoji }}
    </div>
    <div v-show="show" class="Table flex flex-wrap w-[300px] h-[200px]  absolute  overflow-y-auto">
      <div v-for="(emoji,index) in listEmoji" @click="selectEmoji(emoji)" class="Emoji text-[15px] w-[25px] h-[25px] cursor-pointer select-none">{{ emoji }}</div>
    </div>
  </div>

</template>

<script>

export default {
  data() {
    return {
      show: false,
      listEmoji: Array.from({length: 900}, (_, i) => String.fromCodePoint(127808 + (i + 2))),
      emoji: '🍎',
    }
  },
  methods: {
    openEmojiPicker() {
      this.show = !this.show
      document.addEventListener('click', this.closeEmoji)
    },
    closeEmoji(e) {
      if (!this.$el.contains(e.target)) {
        this.show = false
        document.removeEventListener('click', this.closeEmoji)
      }
    },
    selectEmoji(emoji) {
      this.$emit('emoji-selected', emoji)
      this.emoji = emoji
      this.show = false
      document.removeEventListener('click', this.closeEmoji)
    }
  }
}


</script>

<style scoped>
.Table{
  display: flex;
  justify-content: center;
  align-items: center;
  background: peru;
  //border: 2px solid white;
  border-radius: 20px;
  box-shadow: 0px 5px 10px black;
  transition: 0.2s;

}
.Table::-webkit-scrollbar {
  width: 10px;
  height: 5px;
}

.Table::-webkit-scrollbar-track {

}

.Table::-webkit-scrollbar-thumb {
  background: orange;
  border-radius: 20px;
}
.Emoji{
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 20px;
}
</style>