<template>
  <div class="Block" v-if="showBlock" @click="stopTimer">
    <p class="click">click me</p>
  </div>
</template>

<script>
export default {
  props: ["delay"],
  data() {
    return {
      showBlock: false,
      timer: null,
      reactionTime: 0,
    };
  },
  mounted() {
    setTimeout(() => {
      this.showBlock = true;
      this.startTimer();
    }, this.delay);
  },
  methods: {
    startTimer() {
      this.timer = setInterval(() => {
        this.reactionTime += 10;
      }, 10);
    },
    stopTimer() {
      clearInterval(this.timer);
      this.$emit("end", this.reactionTime);
    },
  },
};
</script>

<style>
.Block {
  width: 100px;
  border-radius: 20px;
  background-color: rgb(0, 255, 128);
  color: rgb(0, 0, 0);
  text-align: center;
  margin: 40px auto;
  height: 100px;
}
.click {
  margin-top: 50px;
}
</style>
