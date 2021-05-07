<template>
  <div class="font">
    <div class="color">
      <b-button pill variant="light" b-button size="lg" @click="onClickStart" :pressed.sync="myToggle" v-b-modal.modal-1>
        Laugh AHAHAHAHAHAHAHAHAHAHA
      </b-button>
    </div>
    <div v-if="myToglle">
      <h1>This is a random generated page with a random joke and a random gif. Enjoy!</h1>
      <b-embed
          height="300"
          width="800"
          type="iframe"
          aspect="16by9"
          :src=gif
          allowfullscreen
      ></b-embed>
      <b-button pill variant="light" @click="onClickRandomGif">Reroll gif</b-button>
      <div class="text_color1">
        {{ joke.setup }}
        <div>
          <b-button pill variant="light" @click="onClickPunchLine">See punchline</b-button>
        </div>
        <div class="text_color2">
          {{ punchline }}
        </div>
      </div>
      <div class="font">
        <b-button pill variant="light" @click="onClickRandomJoke">Reroll joke</b-button>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() {
    return {
      joke: Object,
      gif: Object,
      myIframe: null,
      punchline: null,
      myToglle: false
    }
  },
  mounted: function () {
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
  },
  methods: {
    onClickRandomGif() {
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
    },
    onClickPunchLine() {
      this.punchline = this.joke.punchline;

    },
    onClickRandomJoke() {
      fetch('https://official-joke-api.appspot.com/random_joke', {
        method: 'get'
      })
          .then((response) => {
            return response.json()
          })
          .then((jsonData) => {
            this.joke = jsonData
          })
    },
    onClickStart() {
      this.myToglle = true;
    }
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

.font {
  font-family: 'Courier New', monospace;
  color: #bacbe6;
}

.color {
  color: #6f42c1;
}

.text_color1 {
  font-weight: bold;
  font-style: oblique;
  font-size: xx-large;
  color: red;
}

.text_color2 {
  color: lime;
  font-weight: bold;
  font-style: oblique;
  font-size: xx-large;
}

body {
  background-image: url("https://wallpaperaccess.com/download/joker-cartoon-82901");
}
</style>
