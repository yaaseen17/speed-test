<template>
  <p>Reaction time : {{ score }}ms</p>
  <p class="rank">{{ rank }}</p>
</template>

<script>
export default {
  props: ["score"],
  data() {
    return {
      rank: null,
    };
  },
  mounted() {
    if (this.score < 250) {
      this.rank = "Insanely fast";
    } else if (this.score < 400) {
      this.rank = "Super fast";
    } else {
      this.rank = "so slow";
    }
  },
};
</script>

<style>
.rank {
  font-size: 1.4em;
  color: rgb(3, 3, 3);
  font-weight: bold;
}
</style>
