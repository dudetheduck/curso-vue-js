<template>
  <div class="container py-4">
    <div class="row">
      <div class="col">
        <pesquisar-vaga></pesquisar-vaga>
      </div>
    </div>

    <lista-vagas>
      <!--
      <template v-slot:titulo="slotProps">
        {{ slotProps.dadosTitulo.titulo }}
        <hr>
      </template>
      <template v-slot:default="slotProps">
        {{ slotProps.vagas }}
        <hr>
      </template>
      <template v-slot:rodape="slotProps">
        {{ slotProps.dadosRodape.titulo }}
        <hr>
      </template>
      -->
    </lista-vagas>

    <div class="row mt-5">

      <div class="col-4">
        <indicador titulo="Vagas abertas" indicador="100" bg="bg-dark" color="text-white"></indicador>
      </div>

      <div class="col-4">
        <indicador titulo="Profissionais cadastrados" indicador="225" bg="bg-dark" color="text-white"></indicador>
      </div>

      <div class="col-4">
        <indicador  titulo="Visitantes online" :indicador="usuariosOnline" bg="bg-light" color="text-dark"></indicador>
      </div>

    </div>
  </div>
</template>

<script>
import Indicador from '@/components/comuns/Indicador.vue'
import ListaVagas from '@/components/comuns/ListaVagas.vue'
import PesquisarVaga from '@/components/comuns/PesquisarVaga.vue'

  export default {
    name: 'Home',
    components: {
      PesquisarVaga,
      Indicador,
      ListaVagas
    },
    data: () => ({
      usuariosOnline: 0
    }),
    methods: {
      getUsuariosOnline() {
        this.usuariosOnline = Math.floor(Math.random() * 101) // Entre 0 e 100
      }
    },
    created() {
      setInterval(this.getUsuariosOnline, 1000) // A cada 1seg
    }
  }
</script>

<style scoped></style>