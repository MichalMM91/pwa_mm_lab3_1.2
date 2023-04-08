<!-- szablon strony about -->
<template>
    <div class="nav">
        <NuxtLink class="nav-item" to="/">Świat zegarków</NuxtLink>
        <NuxtLink class="nav-item" to="/gallery">Nasza oferta</NuxtLink>
    </div>
  </template>
  
  <script>
  export default {
    name: 'NavPage'
  }
  </script>
  <!-- kod css strony about -->
  <style scoped>
    .nav {
        display: flex;
        flex-wrap: wrap;
        background-color:  rgb(8, 84, 183);
        min-height: 50px;
        max-width: 100vw;
        min-width: 200px;
    }

    .nav-item {
        padding: 15px 15px 10px 15px;
        text-decoration: none;
        color: rgb(196, 198, 196);
    }

    .nav-item:hover {
        color: white;
        background-color:  rgb(7, 60, 130);
    }
    .img-big{
      width:50vw
    }
    .img-small{
      width:80vw;
      display: flex;
    }
  </style>

