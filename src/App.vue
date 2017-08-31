<template>
  <div id="app">
    <div id='color'></div>
    <textatraduire v-on:traduire="api"></textatraduire>
    <traduction v-bind:someData="someData"></traduction>
  </div>
</template>

<script>
import textatraduire from './components/textATraduire'
import traduction from './components/traduction'

export default {
  name: 'app',
  components: {
    textatraduire,
    traduction
  },
  data(){
    return {
      someData:""
    }
  },
  methods:
  { api(texte, langue) {
  // GET /someUrl
  this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20170831T085627Z.1a686b8bcbc27944.bb79ed65e4465c27bb7cda807f83f2e8f62c1ec6&lang=fr-'+langue+'&text='+texte).then(response => {
    // get body data
    this.someData = response.body.text[0];
  }, response => {
    alert("traduction impossible");
  });
}
  }
}
</script>

<style>
  body {
    text-align: center;
    overflow: hidden;
  }

  #color {
    background-color: #46A6A3;
    position: absolute;
    z-index: -1;
    width: 100%;
    height: 40%;
    top: 0;
  }

  #app {
    padding-top: 3em;
    height: 50vh;
  }
</style>
