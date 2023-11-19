<template>
  <v-app id="app">
    <v-container fluid>
      <div class="text-center">
      </div>
      <v-layout row wrap justify-center class="mt-4 pa-2">
        <v-flex xs12 sm10 text-xs-center>
          <v-text-field
            v-model="text"
          ></v-text-field>
        </v-flex>
        <v-flex xs12 sm8 md4 text-xs-center>
          <SpeechInput :text.sync="text" en-US @speechend="speechEnd" />
        </v-flex>
      </v-layout>
    </v-container>
  </v-app>
</template>

<script>
import SpeechInput from "@/components/SpeechInput"

export default {
  name: 'Home',
  components: {
    SpeechInput
  },
  data () {
    return {
      text: '',
      sentences: null
    }
  },
  methods: {
    speechEnd ({sentences, text}) {
      console.log('text', text)
      console.log('sentences', sentences)
      this.sentences = sentences
    }
  }
}
</script>