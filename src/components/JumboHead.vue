<template>
  <section :style="{'background-image': 'url('+ require('../assets/images/illustration-working.svg')+ ')'}">
      <div class="left-bloc">
          <h1 class="left-bloc__heading">More than just shorter links</h1>
          <h3 class="left-bloc__sub-heading">Build your brand's recognition and get detailed insights on how your links are performing</h3>
          <button class="left-bloc__button">Get Started</button>
      </div>

  </section>
</template>

<script>
export default {
    name:"JumboHead" 

}
</script>

<style scoped>
    section{
        display:flex;
        background:src("../assets/images/illustration-working.svg");
        background-repeat: no-repeat;
        background-position: 120%;
        height:600px;
        padding: 0em 10.5em;
        margin-bottom:5em;
    }

    .left-bloc{
        width:40vw;
        color:#302e39;
        margin-top:2em;
    }

    .left-bloc__heading{
        margin-bottom: .3em;
        color:left-bloc__heading;
        font-size: 4.5em;
        font-weight:800;
        line-height:1.1em;
        letter-spacing: -3px;
        
    }
    .left-bloc__sub-heading{
        color:#929199;
        font-weight:300;
    }
    .left-bloc__button{
        margin-top:1em;
        padding:.5em 1.5em;
        background-color:#2bd1d1;
        border-radius:50px;
        box-shadow: none;
        border:none;

        font-size: 1.3em;
        color:white;
        font-weight:600;
    }
    .left-bloc__button:hover
    {
        background-color: #9be3e2;
    }

    @media screen and (max-width:1150px) {
        section{
            align-items: flex-end;
            height:fit-content;
            padding:0 1em;

            background-position:top center;
            background-size: contain;
        }

        .left-bloc{
            width:100%;
            text-align: center;
            margin-top:13em;
            margin-bottom: 4em;
        }
        .left-bloc__heading{
            font-size: 3.5em;

        }

    }


</style>