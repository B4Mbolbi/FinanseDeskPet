<script>
import User from '@/components/Profile/User.vue'
import QrCode from '@/components/Profile/QrCode.vue'

export default {
  components: {User, QrCode},
  data() {
    return{
      ValidUser: true
    }
  }
}


</script>

<template>
  <div class="Profile flex flex-col justify-center items-center gap-3.5">

    <User v-if="ValidUser"></User>
    <QrCode v-else></QrCode>

  </div>
</template>

<style scoped>
.Profile{
  width: 100%;
  height: 100%;
  background:white;
  border-radius: 20px;
}
</style>