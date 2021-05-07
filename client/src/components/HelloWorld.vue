<template>
  <div>
    <b-button>Button</b-button>
    <Iframe>{{gif}}</Iframe>
  </div>
</template>

<script>
import Iframe from "@/components/Iframe";

export default {
  components:{Iframe},
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data(){
    return {
      joke: Object,
      gif: Object,
      myIframe: null
    }
  },
  mounted: function (){
    fetch('https://official-joke-api.appspot.com/random_joke', {
      method: 'get'
    })
        .then((response) => {
          return response.json()
        })
        .then((jsonData) => {
          this.joke = jsonData
        })

    fetch('https://api.giphy.com/v1/gifs/random?api_key=nBhAoIG9unzF0QnysJeOMJ7XWyrADoeZ&tag=&rating=g', {
      method: 'get'
    })
        .then((response) => {
          return response.json()
        })
        .then((jsonData) => {
          console.log(jsonData.data.images)

          this.gif = jsonData.data.embed_url
        })
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
