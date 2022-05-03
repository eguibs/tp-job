<template>
    <section class="more-info">
        <div class="heading">
            <h2 class="heading__title">Advanced Statistics</h2>
            <p class="heading__subtitle">Track how your links are performing across the web with our advanced statistics dashboard</p>
        </div>
        <div class="info-listing">
            <div class="info-listing__background-bar"></div>
            <div class="info-listing__info">
                <div class="info-listing__info__icon">
                    <img :src="require('../assets/images/icon-brand-recognition.svg')" alt=""   >

                </div>
                <h2>Brand Recognition</h2>
                <p>Boost your brand recognition with each click. Generic links don’t 
  mean a thing. Branded links help instil confidence in your content.</p>
            </div>
            <div class="info-listing__info">
                <div class="info-listing__info__icon">
                    <img :src="require('../assets/images/icon-detailed-records.svg')" alt=""   >

                </div>
                <h2>Detailed Records</h2>
                <p>Gain insights into who is clicking your links. Knowing when and where 
  people engage with your content helps inform better decisions.</p>
            </div>
            <div class="info-listing__info">
                <div class="info-listing__info__icon">
                    <img :src="require('../assets/images/icon-fully-customizable.svg')" alt=""   >

                </div>

                <h2>Fully Customizable</h2>
                <p>  Improve brand awareness and content discoverability through customizable 
  links, supercharging audience engagement.</p>
            </div>
        </div>

    </section>
  
</template>

<script>
export default {

}
</script>

<style scoped>
    .more-info{
        display:flex;
        flex-direction: column;
        align-items: center;
        margin:0;
    
        padding:0 10.5em;
        padding-bottom: 5em;
        background-color:#f0f1f6;
        text-align: center;

     
    }
    
    .heading__title{
        font-size: 2.5em;
        margin-top:0;
        margin-bottom:.3em;
    }

    .heading__subtitle{
        color:#a7a7af;
        font-weight:500;
        width:50vw;
    }

    .info-listing{
        display:flex;
        justify-content: space-between;
        position:relative;
        margin-top:5em;
        width:100%;
        height:20em;
    }

    .info-listing__background-bar{
        position:absolute;
        top:50%;
        width:100%;
        height:10px;
        background-color:#2bcfd0;
    }

    .info-listing__info{
        position:relative;
        border-radius:7px;
        width:19vw;
        padding: 3em 2em;
        background-color:white;
        text-align: left;
        font-size: .9rem;
        
    }
    .info-listing__info:nth-child(2){
        align-self: flex-start;
    }
    .info-listing__info:nth-child(3){
        align-self: center;
    }
    .info-listing__info:last-child{
        align-self: flex-end;
    }

     .info-listing__info p {
         color:#929199;
     }

    .info-listing__info__icon{
        position:absolute;
        top:0;
        left:10%;
        padding:1.2em 1.5em;
        transform: translateY(-50%);
        border-radius:50%;
        background-color:#422d54;
    }

    @media screen and (max-width:1150px) {

        .more-info{
            padding:0 1em;
            padding-bottom:5em;
        }

        .heading{
            display:flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
        }

        .heading__subtitle{
            width:100%;
        }

         .info-listing{
             flex-direction: column;
             height: initial;
         }

         .info-listing .info-listing__info{
             align-self: center;
             width:80%;
             margin-bottom: 5em;
         }
         .info-listing .info-listing__info:last-child{
              margin-bottom: 2em;
         }

         .info-listing__background-bar
         {
            position:absolute;
            left:50%;
            top:0;
            width:10px;
            height:80%;
            background-color:#2bcfd0;

         }
    }


</style>