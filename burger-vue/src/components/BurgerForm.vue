<template>
    <div>
      <p>Componente de Mensagem</p>
      <div>
        <form action="" id="burger-form">
            <div class="input-container">
                <label for="nome">Nome do cliente:</label>
                <input type="text" id="nome" name="nome" v-model="nome" placeholder="Digite o seu Nome">
            </div>

            <div class="input-container">
                <label for="pao">Escolha o Pão:</label>
                <select name="pao" id="pao" v-model="pao">
                    <option value="" selected>Selecione o seu pão</option>
                    <option v-for="pao in paes" :key="pao.id" :value="pao.tipo">{{pao.tipo}}</option>
                </select>
            </div>

            <div class="input-container">
                <label for="carne">Escolha a carne do seu Burger:</label>
                <select name="carne" id="carne" v-model="carne">
                    <option value="" selected disabled>Selecione o tipo de carne</option>
                    <option v-for="carne in carnes" :key="carne.id" :value="carne.tipo">{{carne.tipo}}</option>
                </select>
            </div>

            <div class="input-container">
                <label for="opcionais">Selecione os opcionais:</label>
                <div class="checkbox-container" v-for="opcional in opcionaisdata" :key="opcional.id">
                    <input type="checkbox" name="opcional" v-model="opcionais" :value="opcional.tipo" :id="opcional.tipo" class="check-marks">
                    <label :for="opcional.tipo" class="check-label"> {{ opcional.tipo }}</label>
                </div>
            </div>

            <div class="input-container">
                <input type="submit" class="submit-btn" value="Criar meu Burger!">
            </div>
        </form>
      </div>
    </div>
  </template>

<script>
// @ is an alias to /src


export default {
  name: 'BurgerForm',
  components: {
    
  },
  data() {
    return{
        paes: null,
        carnes: null,
        opcionaisdata: null,
        nome: null,
        pao: null,
        carne: null,
        opcionais: [],
        status: "Solicitado",
        msg: null,
    }
  },
  methods:{
    async getIngredientes() {
        const req = await fetch("http://localhost:3000/ingredientes");
        const data = await req.json();

        this.paes = data.paes;
        this.carnes = data.carnes;
        this.opcionaisdata = data.opcionais;
    }
  },
  mounted() {
    this.getIngredientes();
  }
}
</script>

<style scoped>
    #burger-form{
        max-width: 400px;
        margin: 0 auto;
    }

    .input-container{
        display: flex;
        flex-direction: column;
        margin-bottom: 20px;
    }

    label {
        font-weight: bold;
        margin-bottom: 15px;
        color: #222;
        padding: 5px 10px;
        border-left: 4px solid #FCBA03;
    }

    input, select {
        padding: 5px 10px;
        width: 300px;
    }

    #opcionais-container {
        flex-direction: row;
        flex-wrap: wrap;
    }

    .checkbox-container{
        display: flex;
        align-items: flex-start;
        margin-bottom: 20px;
        width: 50%;
        align-items: center;
        margin-top: 10px;
    }

    .check-label{
        border: 0;
        padding: 0;
        margin: 0;
        font-weight: bold;
    }

    .check-marks{
        width: 40px;
    }

    .submit-btn{
        background-color: #222;
        color: #FCBA03;
        font-weight: bold;
        border: 2px solid #222;
        padding: 10px;
        font-size: 16px;
        margin: 0 auto;
        cursor: pointer;
        transition: all 0.4s;
    }

    .submit-btn:hover{
        background-color: transparent;
        color: #222;
    }
</style>