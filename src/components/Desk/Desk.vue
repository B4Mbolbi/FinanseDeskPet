<script>
import Card from '@/components/Desk/Card.vue'
import AddCard from '@/components/Desk/AddCard/AddCard.vue'
export default {
  components: {AddCard, Card},AddCard,
  props:{
    nameDesk: String,
    colorDesk: String,
    nullable: Boolean,
  },
  data() {
    return {
      arr: [],
      toglleAddCard : false
    }
  },
  methods: {
    AddCard(){
      this.toglleAddCard = !this.toglleAddCard
    }
  }
}
</script>

<template>

  <div class="Desk flex flex-row justify-start items-start gap-3.5 p-1 ">
<!--    Header-->
      <div class="Header bg-white rounded-3xl flex justify-start items-start flex-col w-[60%] h-[70%]">
        <h2 class="text-[20px] w-[100%] h-[50px] p-5 text-white font-bold">{{nameDesk}}</h2>
        <AddCard :toggle-close="this.AddCard" :arr-info="this.arr" :color="colorDesk"></AddCard>
      </div>





<!--  Center  -->
    <div class="DescCard h-[100%] w-[100%]">
      <Card
      v-for="(item, index) in arr"
      :key="item.title"
      :title="item.title"
      :date="item.date"
      :teg="item.teg"
      :sum="parseInt(item.sum).toLocaleString()"
      :status="item.status"
      :color="colorDesk"
      @delete-card="arr.splice(index, 1)"
      />

    </div>
  </div>
</template>

<style scoped>
.Desk{
  width: 100%;
  height: 100%;
  border-radius: 20px;

}
.DescCard{
  display: flex;
  flex-wrap: wrap;
  flex-grow: inherit;
  align-content: start;
  gap: 5px;
}
.Header{
  transition: 0.2s;
  background: peru;
}
.DescCard::-webkit-scrollbar {
  width: 10px;
}
.DescCard::-webkit-scrollbar-track {
  background: transparent;
}
.DescCard::-webkit-scrollbar-thumb {
  background: v-bind(colorDesk);
  border-radius: 10px;

}
</style>