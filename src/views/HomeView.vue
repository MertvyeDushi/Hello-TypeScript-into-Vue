<template>
  <div class="home">
    <img
      alt="Vue logo"
      src="../assets/logo.png"
    >

    <HelloComponent msg="Welcome to Your Vue.js + TypeScript App" />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'
import { habrModule } from '@/store'

@Component({
  components: {
    HelloComponent: () => import('@/components/HelloComponent.vue')
  },
  name: 'HomeView'
})

export default class HomeView extends Vue {

  get computedTest() {
    return habrModule.getters.greetingDefault
  }

}

</script>
