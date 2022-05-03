<template>
    <footer>
        <div class="call-to-action" :style="{'background-image': 'url('+ require('../assets/images/bg-boost-desktop.svg')+ ')'}" >
            <h2 class="call-to-action__title">Boost your links today</h2>
            <button class="call-to-action__button">Get Started</button>
        </div>
        <div class="footer-informations">
            <div class="footer-informations__logo">   
                <img class="footer-informations__image" :src="require('../assets/images/logo.svg')" alt="">
            </div>
            <div class="access-links">
                <div>
                    <h3>Features</h3>
                    <ul>
                        <li>Link Shortening</li>
                        <li>Branded Links</li>
                        <li>Analytics</li>
                    </ul>
                </div>
                <div>
                    <h3>Resources</h3>
                    <ul>
                        <li>Blog</li>
                        <li>Developers</li>
                        <li>Support</li>
                    </ul>
                </div>
                <div>
                    <h3>Company</h3>
                    <ul>
                        <li>About</li>
                        <li>Our Team</li>
                        <li>Careers</li>
                        <li>Contact</li>
                    </ul>
                </div>
            </div>
            <div class="social-medias">
                <img :src="require('../assets/images/icon-facebook.svg')" alt="facebook">
                <img :src="require('../assets/images/icon-twitter.svg')" alt="twitter">
                <img :src="require('../assets/images/icon-pinterest.svg')" alt="pinterest">
                <img :src="require('../assets/images/icon-instagram.svg')" alt="instagram">
            </div>
        </div>
    </footer>
</template>

<script>
export default {
    name:"FooterBars"

}
</script>

<style scoped>

    .call-to-action{
        display:flex;
        padding:1.4em;
        padding-bottom: 2em;
        flex-direction: column;
        justify-content:center;
        align-items:center;

        background-color:#3a3053;
        background-repeat: no-repeat;
        background-position: center;
        font-size:1.5em;
        text-align:center;
    }

    .call-to-action__title{
        color:white;
    }

    .call-to-action__button{
        padding:.7em 2em ;
        border-radius:50px;
        border-style:none;

        background-color:#2ccdc7;
        font-size:.8em;
        color:white;    
    }
    .call-to-action__button:hover{
        background-color: #9be3e2;
    }

    .footer-informations{
        display:flex;
        justify-content: flex-end;
        padding:3em 10.5em;
    
        background-color: #232027;
        color:white;
    }

    .footer-informations__image{
        filter: invert(100%) sepia(100%) saturate(0%) hue-rotate(63deg) brightness(107%) contrast(102%);
    }

    .footer-informations__logo{
        margin-right: auto;
    }

    .access-links{
        display:flex;
        justify-self: flex-end;
    }

    .access-links> div{
        margin-right: 80px;
    }

    .access-links> div h3{
        margin-top:0;
    }

    .access-links ul{
        padding:0;
        margin:0;

        list-style: none;
    }

    .access-links li{
        margin-bottom: .8em;

        font-weight: 100;
    }
    .access-links li:hover{
        color:#9be3e2;
    }

    .social-medias >img{
        margin-right:20px;
    }

    .social-medias >img:hover{
        
        filter: invert(69%) sepia(34%) saturate(889%) hue-rotate(131deg) brightness(95%) contrast(85%);
    }

    /* phone rules */
    @media screen and (max-width:1150px) {

        .call-to-action{
            padding:1em;
        }

        .call-to-action__title{
            font-size: 1.1em;
        }

        .footer-informations,
        .access-links{
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding-top:2em;
            
        }

        .footer-informations__logo{
            margin:initial;
          
        }

        .access-links> div{
            margin-right:initial;
            margin-bottom: 2em;

            font-size: .8rem;
            text-align: center;
        }

        .social-medias{
            display:flex;
            justify-content: center;
            gap: 10px;
        }

        .social-medias img {
            margin:0;
        }
    }

</style>