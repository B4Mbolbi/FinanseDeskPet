<script setup>
const info = [
  {
    id: 1,
    title: 'Расходы',
    summ: '10200'
  },
  {
    id: 2,
    title: 'Доходы',
    summ: '12500'
  },
  {
    id: 3,
    title: 'Ивестиции',
    summ: '11500'
  },
  {
    id: 4,
    title: 'Расходы',
    summ: '10200'
  },
  {
    id: 5,
    title: 'Доходы',
    summ: '12500'
  },
  {
    id: 6,
    title: 'Ивестиции',
    summ: '11500'
  },
]



</script>




<template>
  <div class="w-[90%] h-full text-black gap-1 flex flex-col  bg-white rounded-1xl overflow-y-auto">
    <table class="w-[100%] text-[10px] p-2">
      <tr class="bg-gray-500 text-white font-bold rounded-2xl border-b-2">
        <td class="p-1">№</td>
        <td class="p-1">Название</td>
        <td class="p-1 w-[130px]">Сумма Расчетов</td>
      </tr>

      <tr v-for="i in info" class="border-gray-500 border-b-[1px] hover:bg-gray-200">
        <td class="p-1 cursor-pointer ">{{ i.id }}</td>
        <td class="p-1 cursor-pointer ">{{ i.title }}</td>
        <td class="p-1 cursor-pointer ">
          <p class="text-[10px] font-bold w-[50%] h-[20px] flex justify-center items-center bg-green-400 rounded-2xl" >{{ i.summ }} RUB</p>
        </td>
      </tr>


    </table>
  </div>
</template>
