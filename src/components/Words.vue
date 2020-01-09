<template>
  <div class="words">
    <h3>{{word}}</h3>
    <PlayerInput v-bind:word="word" @updateWord="updateWord" />
  </div>
</template>

<script>
import PlayerInput from "./PlayerInput";
export default {
  name: "Words",
  data() {
    return {
      word: this.findWords()
    };
  },
  components: {
    PlayerInput
  },
  methods: {
    updateWord: function() {
      this.word = this.findWords();
    },
    findWords: function() {
      const words = [
        "about",
        "abandon",
        "absolutely",
        "laboratory",
        "leader",
        "letter",
        "library",
        "location",
        "narrow",
        "newspaper",
        "nowhere",
        "separated",
        "service",
        "session",
        "shelter",
        "table",
        "target",
        "thirsty",
        "tomorrow",
        "tourist",
        "element",
        "embarassed",
        "enthusiastically",
        "eventually",
        "everywhere",
        "happily",
        "hesitate",
        "homework",
        "oddly",
        "otherwise",
        "packaging",
        "peaceful",
        "possibility",
        "qualification",
        "reduction",
        "relationship",
        "routine",
        "ultimate",
        "unexpectedly",
        "vocabulary",
        "whisper"
      ];
      const b = words.length;
      const word = words[Math.floor(Math.random() * b)];
      return word;
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
  color: #42b983;
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
