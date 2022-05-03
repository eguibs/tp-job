<template>
<div class="wrapper">
    <section class="shortener">
        <dir class="search-block" :style="{'background-image': 'url('+ require('../assets/images/bg-boost-desktop.svg')+ ')'}">
            <input v-model="linkInput" type="text" name="link" id="link" class="search-block__input-field" :class="{'search-block__input-field--error' : error.state}" placeholder='Shorter a link here...'>
            <input v-on:click.prevent="linkHandler(linkInput)" type="button" value="Shorten it!" class="search-block__input-button">
            <p class="search-block__error-message" v-if="error.state != false">{{ error.message }}</p>
        </dir>
        <div class="search-result" v-if="ApiCallResults != false">
            <div class="search-result__item" v-for="searchResult in searchResults" :key="searchResult.id">
               <p>{{ searchResult.currentSearch}}</p>
               <p>{{ searchResult.shortenedLink}}</p>
               <button @click.prevent='copyToClipboard($event,searchResult.shortenedLink)'>Copy Link</button>
            </div>
        </div>
    </section>
</div>
  
</template>

<script>
export default {
    name:"LinkShortener",
    data:function(){
        return{
            linkInput:"",
            searchResults:[],
            error:{
                state:false,
                message:""
            },
            ApiCallResults:{}
        }
    },
    props:{
        // ApiCallResults: {
        //     type: [Object]
        // }
    },
    methods:{
        copyToClipboard:function(event, result){
            console.log(result);
            navigator.clipboard.writeText(result).then(function() {
                console.log('succés');
                console.log(event.target.innerText);
                event.target.innerText = "copied";
                event.target.classList.toggle("search-result__button__copied")
            }, 
            function(err) {
                console.error('Erreur', err);
            });
        },
        linkHandler:async function (input) {
            if (input !="")
            {
                this.error.state=false;
                this.error.message="";

                await fetch("https://api.shrtco.de/v2/shorten?url="+ input, {
                    method: "GET",
                })
                .then(response =>
                {
                    if (response.ok)
                    {
                        return response.json();
                    }else 
                    {
                        this.error.state=true;
                        this.error.message="Erreur de traitement du lien";
                    }
                })
                .then(json =>
                {
                    if(!json.ok)
                    {
                        this.error.state=true;
                        this.error.message="The link is not valid";   
                    }
                    this.ApiCallResults = json;
                });
            }    
            else{
                this.error.state=true;
                this.error.message="The Url cannot be empty";
            }    
    }
    },
    watch:
    {
        ApiCallResults: function (value) {
            if(value.ok === true)
            {
                let result = {
                    currentSearch: value.result.original_link,
                    shortenedLink: value.result.full_short_link,
                    id: value.result.code
                }
                this.searchResults = [...this.searchResults, result]
                console.log(this.searchResults)
            }
        }
    }
}
</script>

<style scoped>
    .wrapper{
        background-color:#f0f1f6;
    }

    .shortener{
        display:flex;
        position:relative;
        top:-6em;
        flex-direction:column;
        align-items: center;

  
    }

    .search-block{
        display:flex;
        justify-content: space-between;
        flex-wrap: wrap;
      
        min-width:67vw;
        padding:3.5em 4em;
        border-radius:10px;
        background-color:#3a3053;
        background-position: bottom;
        
    }
    .search-block__input-field{

        width:70%;
        padding:.8em 1.5em;
        border-radius:10px;
        border-style: none;

        font-size:1.3em;  
        color:#959597;   
    }

    .search-block__input-button
    {
        padding:.8em 2em;
        border-radius: 10px;
        background-color:#2bd1d1;
        border-style: none;
        color:white;
        font-weight:700;
        font-size:1.3em;
    }
    .search-block__input-button:hover
    {
        background-color: #9be3e2;
    }


    .search-block__error-message{
        width: 100%;
        margin-bottom:0;

        color:red;
        font-style:italic;
    }
    .search-block__input-field--error
    {
        border: solid red 3px ;
    }
    .search-result__item
    {
        box-sizing:border-box;
        display:flex;
        justify-content: flex-end;
        align-items:center;
        min-width:76vw;
        padding:1em 2em;
        border-radius:7px;
        background-color:white;
        font-size:1.2rem;
        margin-bottom: 10px;
    }
    .search-result__item>p:first-child
    {
        margin-right: auto;
    }
    .search-result__item>p:nth-child(2)
    {
        color:#2bd1d1;
    }
    .search-result__item>button{
        margin-left:1em;
        border-radius: 7px;
        border-style:none;
        padding: .8em 1.5em;

        background-color:#2bd1d1;
        color:white;
    }
    .search-result__button__copied{
        background-color:red;
    }

    @media screen and (max-width:1150px) {
        .search-block,
        .search-result__item,
        .search-result{
            width:fit-content;
            margin:1em;
            padding:2em;
        }

        .search-block__input-field,
        .search-block__input-button{
            width:100%;
        }

        .search-block__input-field{
            margin-bottom: 20px;
        }
        .search-result
        {
            display:flex;
            flex-direction: column;
            align-items: stretch;
            width:90%;
            margin-top:0;
         
        }
        .search-result__item
        {
             flex-direction: column;
             align-items:stretch;
             margin:0;
             margin-bottom:1em;
             padding:1em;
             width:100%;
        }
        .search-result__item:last-child{
             margin-bottom:0;
         }

        .search-result__item>p:first-child
        {
            margin:initial;
        }
        .search-result__item>button
        {
            margin:0;
        }

    
    }

</style>