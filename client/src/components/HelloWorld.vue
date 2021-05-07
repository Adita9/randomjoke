<template>
  <div>
    <h1>This is a random generated page with a random joke and a random gif. Enjoy!</h1>
    <div>
      {{ joke.setup }}
      <div>
        <b-button @click="onClickPunchLine">See punchline</b-button>
      </div>
      <div>
        {{ punchline }}
      </div>
      <div>Do you want another random joke?
        <b-button @click="onClickRandomJoke">Reroll joke</b-button>
      </div>
      <b-embed
          height="500"
          width="500"
          type="iframe"
          aspect="1by1"
          :src=gif
          allowfullscreen
      ></b-embed>
      <b-button @click="onClickRandomGif">ReRandomGif</b-button>
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
      punchline: null
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
    onClickRandomJoke(){
      fetch('https://official-joke-api.appspot.com/random_joke', {
        method: 'get'
      })
          .then((response) => {
            return response.json()
          })
          .then((jsonData) => {
            this.joke = jsonData
          })
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
</style>
