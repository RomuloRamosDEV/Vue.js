<template>  

  <div>
    <Header/>

    <PrimeiroComponente/>

    <LifeCycle/>
    <Pessoa/>
    <Form />
  </div>

</template>

<script>

  import PrimeiroComponente from './components/PrimeiroComponente.vue';
  import LifeCycle from './components/LifeCycle.vue';
  import Pessoa from './components/Pessoa.vue';
  import Header from './components/Header.vue';
  import Form from './components/Form.vue';


  export default{
    name: 'App',
    components: {
    PrimeiroComponente,
    LifeCycle,
    Pessoa,
    Header,
    Form
}
  }
</script>

<style>
  body {
    background-color: #333;
    color: white;
  }

  a {
    color: red;
  }
</style>