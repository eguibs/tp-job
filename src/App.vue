<template>
  <main class="container">
    <nav-bar></nav-bar>
    <jumbo-head></jumbo-head>
    <link-shortener></link-shortener>
    <more-info></more-info>
    <footer-bars></footer-bars>
  </main> 
</template>

<script>

import NavBar from "./components/NavBar.vue";
import JumboHead from "./components/JumboHead.vue";
import LinkShortener from './components/LinkShortener.vue';
import MoreInfo from './components/MoreInfo.vue';
import FooterBars from "./components/FooterBars.vue";

export default {
  name: 'App',
  components: {
    NavBar,
    JumboHead,
    LinkShortener,
    MoreInfo,
    FooterBars
  },
  data:function () {
    return {
      ApiCallResults:false
    }
  }
}
</script>

<style >

@font-face{
  font-family: "Poppins";
  src: local("Poppins"),
  url(./fonts/Poppins/Poppins-Regular.ttf) format("truetype");
  font-weight:500;
}
@font-face{
  font-family: "Poppins";
  src: local("Poppins"),
  url(./fonts/Poppins/Poppins-Bold.ttf) format("truetype");
  font-weight:600;
}
body{
  margin:0;
  font-family: "Poppins";

}
h2{
  color:#302e39;
}

.main-section{
  background-color:grey;
}
</style>
