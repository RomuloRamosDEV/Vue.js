<template>
  <div id="main-banner">
    <h1>Faça Seu Burger</h1>
  </div>
</template>

<script>
// @ is an alias to /src


export default {
  name: 'Banner',
  components: {
    
  }
}
</script>

<style scoped>
  #main-banner{
    background-image: url('/./public/img/burger.jpg');
    background-position: 0 -250px;
    background-size: cover;
    height: 800px;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  #main-banner h1{
    color: #FFF;
    text-align: center;
    font-size: 60px;
    background-color: #222;
    margin-right: auto;
    padding: 15px 50px;
  }
</style>