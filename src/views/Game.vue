<template>
  <div>
    <h1>{{ message }}</h1>
    <Play
      v-for="s in stuff"
      :class="s"
      :key="s.index"
      :msg="s"
      @thichyo="doThis"
    ></Play>
  </div>
</template>
<script>
import Play from "@/components/Play";

export default {
  data() {
    return {
      stuff: ["Rock", "Paper", "Scissor", "Lizard", "Spock"],
      message: "Start The Game By Clicking Any Icon",
    };
  },
  methods: {
    doThis(msg) {
      let randomInt = Math.floor(Math.random() * 5);
      let computerSelected = this.stuff[randomInt];
      this.message = this.checkWinner(msg, computerSelected);
    },
    checkWinner(user, computer) {
      console.log(
        "\n User selected: ",
        user,
        "\n Computer selected: ",
        computer
      );
      if (user === computer) {
        return "Tied";
      }
      switch (user) {
        case "Rock":
          switch (computer) {
            case "Scissor":
            case "Lizard":
              return "User Won";
            case "Spock":
            case "Paper":
              return "Computer Won";
          }

        case "Paper":
          switch (computer) {
            case "Rock":
            case "Spock":
              return "User Won";
            case "Scissor":
            case "Lizard":
              return "Computer Won";
          }

        case "Scissor":
          switch (computer) {
            case "Paper":
            case "Lizard":
              return "User Won";
            case "Spock":
            case "Rock":
              return "Computer Won";
          }

        case "Lizard":
          switch (computer) {
            case "Paper":
            case "Spock":
              return "User Won";
            case "Scissor":
            case "Rock":
              return "Computer Won";
          }

        case "Spock":
          switch (computer) {
            case "Rock":
            case "Paper":
              return "User Won";
            case "Lizard":
            case "Scissor":
              return "Computer Won";
          }
      }
    },
  },
  components: { Play },
};
</script>

<style></style>
