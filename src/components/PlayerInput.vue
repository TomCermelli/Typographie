<template>
  <div>
    <input id="playerText" type="text" v-model="playerText" v-on:keyup="checkWord" />
    <h3>{{score}}</h3>
  </div>
</template>

<script>
export default {
  name: "PlayerInput",
  data() {
    return {
      playerText: "",
      score: 0,
      i: 0
    };
  },
  props: {
    newWord: String

  },
  methods: {
    checkWord: function() {
      if (this.playerText == this.newWord) {
        this.$emit("findNewWord");
        this.playerText = ""; 
        this.score += 1;
        this.i = 0;
        return;
      }
      if (this.playerText[this.i] !== this.newWord[this.i]){
        this.playerText = "";
        this.i = 0;
        return;
      }
      this.i++;
      }
    }
  };
</script>

<style>
</style>
