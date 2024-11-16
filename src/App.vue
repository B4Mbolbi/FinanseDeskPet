<template>
  <div class="General flex-row">
    <auth :data="posts"></auth>

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
import auth from '@/components/autorize/auth.vue'
import axios from 'axios'
export default {
  components: {
    auth
  },
  data() {
    return {
      posts:'',
      errors:[]
    }
  },

  async mounted() {
    const response = await axios.get(`http://192.168.0.14/`)
    this.posts = response.data.hash

  }
}
</script>
