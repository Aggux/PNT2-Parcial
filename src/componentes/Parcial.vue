<template>
  <section class="src-componentes-parcial">
    <div class="jumbotron">
      <h1>Parcial PNT2</h1>

    <div class="form-group">
        <input class="form-control" id="texto" type="text" v-model.trim="texto">
    </div>
    
    <div>Cantidad de caracteres: {{this.cantidadCaracteres}}</div>
    <br>
    <!-- <div>1. - {{this.codificado()}}</div>
    <div>2. - {{this.todoMayuscula()}}</div>
    <div>3. - {{this.todoMinuscula()}}</div>
    <div>4. - {{this.mayusculaMinuscula()}}</div>
    <div>5. - {{this.minusculaMayuscula()}}</div> -->

    <div class="table-responsive">
      <table class="table table-dark">
        <tr>
          <th>1.Codificado</th>
          <th>2.Mayuscula</th>
          <th>3.Minuscula</th>
          <th>4.May/Min</th>
          <th>5.Min/May</th>
        </tr>
        <tr>
          <td>{{this.codificado()}}</td>
          <td>{{this.todoMayuscula()}}</td>
          <td>{{this.todoMinuscula()}}</td>
          <td>{{this.mayusculaMinuscula()}}</td>
          <td>{{this.minusculaMayuscula()}}</td>
        </tr> 
      </table>

      <hr>

      <table class="table table-dark">
        <tr>
          <th>Número de pregunta</th>
          <th>Respuesta</th>
        </tr>
          <td>
            1
          </td>
          <td>
            c
          </td>
        <tr>
          </tr>
          <td>
            2
          </td>
          <td>
            c
          </td>
        <tr>
          </tr>
          <td>
            3
          </td>
          <td>
            a
          </td>
        <tr>
        </tr>
      </table>
    </div>
    </div>
  </section>
</template>

<script lang="js">

  export default  {
    name: 'src-componentes-parcial',
    props: [],
    mounted () {

    },
    data () {
      return {
        texto:"",
      }
    },
    methods: {
      todoMayuscula(){
        return this.texto.toUpperCase()
      },
      todoMinuscula(){
        return this.texto.toLowerCase()
      },
      minusculaMayuscula(){
      let textoMinMay = ""
        for(let i = 0; i< this.texto.length; i++){
        if(i%2 == 0)
            textoMinMay += this.texto[i].toLowerCase()        
        else
            textoMinMay += this.texto[i].toUpperCase()             
        }
        return textoMinMay
      },
      mayusculaMinuscula(){
        let textoMayMin = ""
        for(let i = 0; i< this.texto.length; i++){
        if(i%2 != 0)
            textoMayMin += this.texto[i].toLowerCase()        
        else
            textoMayMin += this.texto[i].toUpperCase()             
        }
        return textoMayMin
      },
      codificado(){
        let textoCodificado = ""
        for(let i = 0; i< this.texto.length; i++){
          switch (this.texto[i]) {
            case "a":
              textoCodificado += "u"
              break;
            case "e":
              textoCodificado += "o"
              break;
            case "o":
              textoCodificado += "e"
              break;
            case "u":
              textoCodificado += "a"
              break;
            default:
              textoCodificado += this.texto[i]
              break;
          }
        }
        return textoCodificado.toLowerCase()
      }

    },
    computed: {
      cantidadCaracteres(){
        return this.texto.length
      },
    }
}


</script>

<style  lang="css">
  .jumbotron {
    background-color: blueviolet;
    color: white;
  }

h2 {
    color: white;
}

hr {
    background-color: #eee;
}

label {
    text-transform: capitalize;
}

pre {
    color: white;
}
</style>
