<template>
  <div>
    <img :src="getSource" :alt="msg" @click="clicked" />
  </div>
</template>
<script>
export default {
  props: {
    msg: String,
  },
  data() {
    return {
      // source: "",
    };
  },
  methods: {
    clicked() {
      this.$emit("thichyo", this.msg);
    },
  },
  computed: {
    getSource() {
      return require(`@/assets/rpsls/${this.msg}.png`);
    },
  },
};
</script>
