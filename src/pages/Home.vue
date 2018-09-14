<template>
  <div class="home">
    <div class="text">
      <h1>Bem vindo.</h1>
      <p>	Lorem ipsum sed pharetra, molestie quis. </p>
    </div>
  </div> 
</template>

<script>
export default {
  name: 'Home',
  props: {
    home: String,
  }
  
}
</script>

<style scoped>

  .home {
    width: 100%;
    height: 100vh;
    background-image: url('http://placekitten.com/1280/840');
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
    box-sizing: border-box;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .text {
    text-transform: uppercase;
    color: white;
    font-weight: 700;
  }

  h1 {
    font-size: 60px;
  }

</style>
