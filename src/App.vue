<template>

  <Grid>
    <template v-slot:profile>
      <Profile></Profile>
    </template>

    <template v-slot:Adddesk>
      <CreaateDesk :listDesk="arrDesk" :toggle-desc="Desk" @update:toggle-desc="updateDesk"></CreaateDesk>
    </template>
      <template v-slot:desk>
        <div v-if="arrDesk.length === 0">
          У вас нет доступных расчетов 😐
        </div>
        <template v-else>
          <Desk v-show="TogDesk?.name === desk?.name"
                v-for="desk in arrDesk" :key="desk.name"
                :name-desk="desk.name"
                :color-desk="desk.colorDesck"
                :nullable="true"></Desk>
        </template>
      </template>

  </Grid>


</template>

<script setup>
import Grid from './components/Grid/Grid.vue'
import Profile from '@/components/Profile/Profile.vue'
import Desk from '@/components/Desk/Desk.vue'
import CreaateDesk from '@/components/Desk/CreaateDesk.vue'
import {ref} from 'vue'
const TogDesk = ref({
  name: '',
  colorDesck: ''
})

function updateDesk(newDesk) {
  TogDesk.value = newDesk
}

</script>


<script>
export default {
  data() {
    return {
      arrDesk: [],
    }
  }

}
</script>

