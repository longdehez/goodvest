<template>
  <div class="wrapper">
    <div class="hero">
      <Sidebar/>
    </div>  
  </div>
</template>

<script>
  import Sidebar from '../components/Sidebar'

  export default {
    components: {
      Sidebar,
    }
  }
</script>

<style lang="scss">

@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;700&display=swap');

  html,body{
    margin : 0;
    padding: 0;
    font-family: 'Montserrat', sans-serif;
    box-sizing: border-box;
  }

  *,
  *:before,
  *:after {
    box-sizing: inherit;
    margin: 0;
    padding: 0;
    outline: 0;
  }

  p{
    margin: 0;
    padding: 0;
    font-size: 12px;
  }

  h3{
    margin: 0;
    padding: 0;
    font-size: 14px;
    font-weight: bold;
  }

  .wrapper{
    width: 100%;
    height: 100%;
    margin-top: 10px;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .hero{
    width: 1200px;
    height: 800px;
    background: #e3eef1;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: flex-start;
    border-radius: 16px;
    padding: 0 450px;
  }

  span{
    margin: 0;
    padding: 0;
  }
</style>
