<template>
  <div id="app" class="flex items-center justify-center h-screen bg-gray-50">
    {{ cepData }}
  </div>
</template>

<script>
import { consultarCep } from 'correios-brasil'

export default {
  name: 'App',
  data () {
    return {
      cep: '',
      cepData: {},
    }
  },
  metaInfo: {
    title: 'Consultar CEP',
    titleTemplate: '%s | Template',
    htmlAttrs: {
      lang: 'pt-br',
    }
  },
  created () {
    this.cep = prompt('Digite o CEP')
    consultarCep(this.cep).then(response => this.cepData = response)

  },
}
</script>

<style lang="postcss">
#app {
  font-family: 'Montserrat', sans-serif;
}
</style>
