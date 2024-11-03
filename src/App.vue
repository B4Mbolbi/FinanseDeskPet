<template>
  <div class="General flex-row">
    <Desk></Desk>

  </div>
</template>

<style scoped>
*{
  margin: 0;
  padding: 0;
  transition: .5s;
  display: flex;
}
.General {
  width: 100%;
  height: 100vh;
  background-image: url("./assets/fone.jpg");
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;

}
</style>


<script>
import Desk from '@/components/Desk/Desk.vue'
export default {
  components: {Desk}

}
</script>
