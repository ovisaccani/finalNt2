<template>
  <div class="hello">
    <input type="text" v-model="valor" />
    <br />
    <div v-if=muestro>
      <li>Cantidad: {{ caracteres }}</li>
      <li>{{ codificado() }}</li>
      <li>{{ todoMayuscula() }}</li>
      <li>{{ todoMinuscula() }}</li>
      <li>{{ alternarTexto() }}</li>
      <li>{{ alternarTextoDos() }}</li>
    </div>

    <p>respuestas: 1:b 2:b, 3:c, 4:b, 5:b .... </p>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {},
  data() {
    return {
      valor: "",
      mostrar: true,
    };
  },
  methods: {
   
   codificado(){
      let cadenaNueva = this.valor.toLowerCase()
      cadenaNueva = Array.from(cadenaNueva) 

      for (let i = 0; i < cadenaNueva.length; ++i) {
        if (cadenaNueva[i] == "a") {
          cadenaNueva[i] = "u"
        } else if (cadenaNueva[i] == "e"){
          cadenaNueva[i] = "o"
        } else if (cadenaNueva[i] == "o"){
          cadenaNueva[i] = "e"
        } else if (cadenaNueva[i] == "u"){
          cadenaNueva[i] = "a"
      }
      }

      return cadenaNueva.join('') + " (Codificado)";
    },  

    todoMayuscula() {
      let texto = this.valor.toUpperCase() + " (Mayuscula)";
      return texto;
    },
    todoMinuscula() {
      let texto = this.valor.toLowerCase() + " (Minuscula)";
      return texto;
    },
    alternarTexto() {
      let resultado = "";

      for (let i = 0; i < this.valor.length; ++i) {
        if (i % 2 == 0) {
          resultado += this.valor[i].toUpperCase();
        } else {
          resultado += this.valor[i].toLowerCase();
        }
      }

      return resultado + " (Mayuscula/Minuscula)";
    },
    alternarTextoDos() {
      let resultado = "";

      for (let i = 0; i < this.valor.length; ++i) {
        if (i % 2 == 0) {
          resultado += this.valor[i].toLowerCase();
        } else {
          resultado += this.valor[i].toUpperCase();
        }
      }

      return resultado + " (Minuscula/Mayuscula)";
    },
  },
  computed: {
      caracteres(){
      let cant = this.valor.length
      return cant
    },
    muestro(){
      return this.valor.length!=0
    }
  },
};
</script>

<style scoped>
.jumbotron {
  background-color: rgb(224, 194, 224);
  color: white;
}

hr {
  background-color: #eee;
}
</style>
