<template>
<div class="container text-center">
   <div class="row">    
    <div class="col-md-12 bg-success p-2 text-dark bg-opacity-25">
      <div class="row">
        <div class="col-8">
          <label><h2>Resultado</h2></label>
          <input class="form-control form-control-lg mt-3 mb-3 text-end" type="text" :value="result" placeholder="Valor" aria-label=".form-control-lg example" disabled>
          <label><h3>Número 1</h3></label>
          <input class="form-control form-control-lg mt-3 mb-3 text-end" type="text" v-model="numOne" placeholder="Valor"  @focus="clear()"  aria-label=".form-control-lg example">
          <label><h3>Número 2</h3></label>
          <input class="form-control form-control-lg mt-3 mb-3 text-end" type="text" v-model="numTwo" placeholder="Valor" aria-label=".form-control-lg example">
        </div>
        <div class="col-4">
          <ul class="list-group">
                <li class="list-group-item"><button type="submit" class="btn btn-success mb-3" @click="numberAdd()">+<br>(Somar)</button></li>
                <li class="list-group-item"><button type="submit" class="btn btn-success mb-3" @click="numberDecrease()">-<br>(Diminuir)</button></li>
                <li class="list-group-item"><button type="submit" class="btn btn-success mb-3" @click="numberMultiply()">*<br>(Multiplicar)</button></li>
                <li class="list-group-item"><button type="submit" class="btn btn-success mb-3" @click="numberDivide()">/<br>(Dividir)</button></li>
                <li class="list-group-item"><button type="submit" class="btn btn-info mb-3" @click="clear()">Limpar</button></li>
              </ul>
         </div>
      </div>     
    </div>        
  </div>
</div>
  
</template>

<script>
export default ({
  name: 'App',
  data () {
    return {      
      result: 0,
      valueNumber: '',
      numOne: '',
      numTwo: '',
    }  
  }, 
  methods: {
    numberDecrease(){
      this.result = parseFloat(this.numOne) - parseFloat(this.numTwo);      
    },
    numberAdd(){
      this.result = parseFloat(this.numOne) + parseFloat(this.numTwo);      
    },
    numberMultiply(){  
      this.result = parseFloat(this.numOne) * parseFloat(this.numTwo);      
    },
    numberDivide(){  
      if (parseFloat(this.numTwo) > 0) {
        this.result = parseFloat(this.numOne) / parseFloat(this.numTwo);
      } else {
        this.result = 'ERRO';
      }            
    },
    clear(){
      this.result = '';
      this.numOne = '';
      this.numTwo = '';
    }
 }
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
