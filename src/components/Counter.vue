<template>
  <h2>{{ customTitle }}</h2>
  <p>{{ counter }} <sup>2</sup> = {{  squareCounter }}</p> <!--la etiqueta sup, sirve para poner exponentes -->
  <div>
    <button @click="increment">+1</button>
    <button @click="decrement">-1</button>
  </div>

</template>

<script>
export default {
    //propetis de cada componente
    // props: {
    //     title: String,
    //     start:{
    //          type: Number,
    //          default: 100,
    //          validator( value ){
    //             return value > 0
    //          }
    //     },
    // },
    name: 'CounterComponent',
    data (){
        return {
            counter: this.start //iniciando conuter con el numero que le mando en start
        }
    },
    methods:{
        getSquareValue() {
            console.log('getSquareValue')
            return this.counter * this.counter
        },
        increment() {
            return this.counter ++
        },
        decrement() {
            return this.counter --
        }
    },
    computed: { //se guarda en el cachet
        squareCounter() {
            console.log('computed squareCounter')
            return this.counter * this.counter
        },
        customTitle() {
            return this.title || 'Counter' //condiciones metodo ternario, si title no esta vacio lo musestra si esta vacio muestra 'Counter'   
        }
    }

}
</script>

<!-- <style>
    button{
        background-color: #64BB87;
        border-radius: 5px;
        color: white;
        cursor:pointer;
        margin: 0 5px;
        padding: 5ps 15px;
        transition: 0.3s ease-in-out;
    }

    button:hover{
        background-color: #5aa67b;
        transition: 0.3s ease-in-out;
    }
</style> -->

