<script>
import ListFunck from '@/components/FuncList/ListFunck.vue'
import Profile from '@/components/FuncList/Profile.vue'
import RootDesk from '@/components/Desck/RootDesk.vue'
export default {
  components: {RootDesk, ListFunck, Profile},
  methods: {},
  
}
</script>

<template>

<div class="w-[100%] h-[100vh] bg-black flex flex-row text-white p-1 gap-3.5" style="background: #01874f">
  <div class="w-[20%] h-[100%] flex flex-col gap-3.5">
    <Profile></Profile>
    <ListFunck></ListFunck>
  </div>
  <RootDesk></RootDesk>
</div>

</template>

