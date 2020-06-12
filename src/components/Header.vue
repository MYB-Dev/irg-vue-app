<template>
  <header>
    <div class="nav">
      <img src="../assets/logo.png" alt="logo" >
      <h1>Calculez IRG 2020</h1>
    </div>
    <hr />
  </header>
</template>

<script>
export default {
  name: 'Header',
};
</script>

<style>
  .nav{
    display: flex;
    margin-bottom: 30px;
    justify-content: center;
  }
  img{
    width: 10rem;
    height: 8rem;
  }
  h1{
    padding-top: 10px;
  }
</style>
