<template>
  <p>Reaction Time {{ score }} ms</p>
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
      this.rank = "thumbs up";
    } else if (this.score < 400) {
      this.rank = "Rapid reflexes";
    } else {
      This.rank = "snail pace";
    }
  },
};
</script>

<style>

</style>