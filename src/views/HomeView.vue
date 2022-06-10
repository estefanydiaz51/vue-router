<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <TitleComponent title="Página de Inicio"></TitleComponent>
  </div>
</template>

<script>
import TitleComponent from '../components/TitleComponent'
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'HomeView',
  components: {
    TitleComponent,
    HelloWorld
  }
}
</script>
