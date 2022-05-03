<template>
  <header>
    <div class="nav-logo">
      <a class="nav-logo__image" href="./index.html"><img :src="require('../assets/images/logo.svg')"></a>
    </div>
    <div class="nav">
      <ul class="nav-left__nav-items">
        <li class="nav-left__nav-items__item">Feature</li>
        <li class="nav-left__nav-items__item">Pricing</li>
        <li class="nav-left__nav-items__item">Resources</li>
      </ul>
      <hr class="nav-left__nav-separator">
      <ul class="nav-right__nav-items">
        <li class="nav-right__nav-items__item">Login</li>
        <li class="nav-right__nav-items__item  nav-right__nav-items__item--rounded">SignUp</li>
      </ul>
    </div>
    <div class="burger-menu" @click="togglePhoneMenu">
      <button class="burger-menu__button"><img :src="require('../assets/images/menu.png')" alt="menu-icon"></button>
    </div>
     
  </header>
</template>

<script>
export default {
  name:"NavBar",
  methods:{
    togglePhoneMenu:function () {
      document.getElementsByClassName("nav")[0].classList.toggle("displayed");
    }
  }
}
</script>

<style scoped>
  header{
    display:flex;
    /* position:relative; */
    justify-content: space-between;
    margin: 3em 10.5em ;
    color:#929199;
  }

  .nav-logo,
  .nav{
    display:flex;
    align-items:center;
  }

  .nav{
    width:100%;
  }

  .nav-left__nav-items,
  .nav-right__nav-items{
    display:flex;
    align-items: center;
    list-style: none;
    margin:0 1em;

    font-weight: 700;
  }

  .nav-right__nav-items__item,
  .nav-left__nav-items__item{
    margin:0 1em;
  }

  .nav-left__nav-separator{
    display:none;
  }

  .nav-left__nav-items{
    margin-right: auto;
  }

  .nav-right__nav-items__item--rounded{
    padding:.5em 1.5em;
    border-radius:60px;

    background-color:#2bd1d1;
    color:white;
  }
  .nav-right__nav-items__item--rounded:hover
  {
    background-color: #9be3e2;
  }

  .burger-menu{
    display:none;
  }

  .burger-menu__button{
    background-color:transparent;
    border:none;
   
  }

  .burger-menu img{
      width:3em;
    }

  @media screen and (max-width:1150px) { 

    header{
      margin:2em 1.5em;
    }

    .burger-menu{
      display:block;
    }
    
    .nav{ 
      opacity: 0;
      transition: opacity 200ms ease ;
      position:absolute;
        top:4.5em;
        left:2.5%;
        right:2.5%;
        width:initial;
        /* width:95%; */
      padding:2em 0;  
      flex-direction: column;
      justify-content: space-around; 
      align-items: center;
      border-radius:10px;

      background-color:#3a3053;
      color:white;
      font-weight:900;
      font-size:1.3rem;
    }
    .nav.displayed{
      opacity: 1;
      transition: opacity 200ms ease ;
    }
    .nav-left__nav-items,
    .nav-right__nav-items{
      flex-direction: column;
      align-items: center;
      margin:0;
      padding:0;
    }

    .nav-right__nav-items__item,
    .nav-left__nav-items__item{
      margin-bottom:1em;
    }

    .nav-left__nav-separator{
      display:block;
      margin:auto;
      width:80%;
    }

  }

</style>