<template>
  <div>
    <input id="playerinput" type="text" v-model="playerinput" v-on:keyup="checkWord" />
    <h3>{{score}}</h3>
  </div>
</template>

<script>
export default {
  name: "PlayerInput",
  data() {
    return {
      playerinput: "",
      score: 0
    };
  },
  props: {
    word: String
  },
  methods: {
    checkWord: function() {
      if (this.playerinput == this.word) {
        this.$emit("updateWord");
        this.playerinput = "";
        this.score += 1;
      }
    }
  }
};
</script>

<style>
</style>
