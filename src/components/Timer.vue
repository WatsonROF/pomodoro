<template>
  <div>
    {{minutos}}:{{segundos}}
    <ButtonComecar @iniciar-timer="iniciarTimer" />
    <ButtonIntervalo @iniciar-intervalo="iniciarIntervalo" />
  </div>
</template>

<script>
import ButtonComecar from "./ButtonComecar.vue"
import ButtonIntervalo from "./ButtonIntervalo.vue"
import xaropinho from "../assets/xaropinho.mp3"

export default {
  name: 'Timer',
  components: {
    ButtonComecar,
    ButtonIntervalo
  },
  data() {
    return { 
      minutos: 0,
      segundos: 0,
      audioXaropinho: new Audio(xaropinho),
      tocou: true,
      contadorDia: 0,
      contadorPomodoros: 0
    }
  },
  methods: {
    funcaoDecrementar() {
      setInterval(() => {
        if(this.minutos === 0 && this.segundos === 0) {
          clearInterval()
          if(this.tocou) {
            this.audioXaropinho.play()
            this.tocou = !this.tocou
          }
        }
        else if(this.segundos === 0) {
          this.minutos = this.minutos - 1
          this.segundos = 59
        }
        else {
          this.segundos = this.segundos - 1
        }
      }, 1000)
    },
    iniciarTimer() {
      this.contadorDia = this.contadorDia + 1
      this.contador = this.contador + 1
      this.tocou = true
      this.minutos = 25
      this.segundos = 0
      this.funcaoDecrementar()
    },
    iniciarIntervalo() {
      this.tocou = true
      this.minutos = 5
      this.segundos = 0
      this.funcaoDecrementar()
    }
  },
}
</script>

<style scoped>

</style>
