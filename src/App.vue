<template>
  <div class="container">
    <div class="row">
      <div class="col-sm-12">
        <nav-header @pageWasChanged="currentPage = $event"></nav-header>
        <keep-alive>
          <component v-bind:is="currentPage"></component>
        </keep-alive>
        <cc-footer>
          <p class="text-center">{{appName}}</p>
          <ul class="nav justify-content-center">
            <li class="nav-item"><a class="nav-link">Home</a></li>
            <li class="nav-item"><a class="nav-link">About us</a></li>
            <li class="nav-item"><a class="nav-link">Contact us</a></li>
          </ul>
        </cc-footer>
      </div>
    </div>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import CardFront from "./components/card/CardFront.vue";
import CardInsideLeft from "./components/card/CardInsideLeft";
import CardInsideRight from "./components/card/CardInsideRight";
import CardBack from "./components/card/CardBack";
import Footer from "./components/Footer";

export default {
  data: function(){
    return{
      currentPage: 'cardFront',
      appName: 'Creative Cards'
    }
  },
  components:{
    navHeader:Header,
    cardFront:CardFront,
    cardInsideLeft:CardInsideLeft,
    cardInsideRight:CardInsideRight,
    cardBack:CardBack,
    ccFooter:Footer
  }
}
</script>

<style>
body{
  font-family: Verdana, Geneva , sans-serif;
  color: #333;
}
a{
  cursor: pointer;
}
</style>
