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
      let randomInt = Math.floor(Math.random() * 3);
      let computerSelected = this.stuff[randomInt];
      console.log(this.checkWinner(msg, computerSelected));
    },
    checkWinner(user, computer) {
      if (user === computer) {
        return "Tied";
      }
      switch (user) {
        case "Rock":
          switch (computer) {
            case "Paper":
              return `Computer chose ${computer}, User chose ${user}. Computer Won`;
            case "Scissor":
              return `Computer chose ${computer}, User chose ${user}. User Won`;
          }

        case "Paper":
          switch (computer) {
            case "Rock":
              return `Computer chose ${computer}, User chose ${user}. Computer Won`;
            case "Scissor":
              return `Computer chose ${computer}, User chose ${user}. User Won`;
          }

        case "Scissor":
          switch (computer) {
            case "Rock":
              return `Computer chose ${computer}, User chose ${user}. Computer Won`;
            case "Paper":
              return `Computer chose ${computer}, User chose ${user}. User Won`;
          }
      }
    },
  },
  components: { Play },
};
</script>
