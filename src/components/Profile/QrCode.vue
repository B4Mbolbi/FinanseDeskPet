<style scoped>
.Qr{
  width: 150px;
  margin-right: 20px;
  margin-left: 20px;
  background: v-bind(background);
  padding: 10px;
  border-radius: 10px;
}
.QRBlock{
  background: linear-gradient(30deg,#0088CC,#F7F7F7);
}
</style>

<template>
  <div class="QRBlock flex flex-row justify-center items-center w-full h-full rounded-xl">
    <qrcode-vue class="Qr" :value="value" :background="background" :size="size" level="H" render-as="svg" />
    <div class="flex flex-col justify-center">
      <h1 class="text-base text-white">Привет 🎉</h1>
      <p class="text-base text-blue-600">
        Зарегистрируйся через нашего бота в <p class="text-[#0088CC] text-xl">Telegram </p>
      </p>
    </div>

  </div>

</template>
<script>
import QrcodeVue, { QrcodeCanvas, QrcodeSvg } from 'qrcode.vue'

export default {
  data() {
    return {
      value: 'https://example.com',
      size: 100,
      background: '#fff',
    }
  },
  components: {
    QrcodeVue,
    QrcodeCanvas,
    QrcodeSvg,
  },
}
</script>

