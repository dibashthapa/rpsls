<template>
  <div>
    <h1>hello</h1>
    <Play v-for="s in stuff" :key="s.index" :msg="s" @thichyo="doThis"></Play>
  </div>
</template>
<script>
import Play from "@/components/Play";

export default {
  data() {
    return {
      stuff: ["Rock", "Paper", "Scissor", "Lizard", "Spock"],
    };
  },
  methods: {
    doThis(msg) {
      console.log("User Clicked " + msg);
    },
  },
  components: { Play },
};
</script>
