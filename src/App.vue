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

<div class="Wrapper w-[100%] h-[100vh] text-white flex flex-row p-1 gap-3.5">
  <div class="w-[20%] h-[100%] flex flex-col gap-3.5">
    <Profile></Profile>
    <ListFunck></ListFunck>
  </div>
  <RootDesk></RootDesk>
</div>

</template>

<style>

.Wrapper{
  background-image:url('src/assets/fone.jpeg');
}
</style>