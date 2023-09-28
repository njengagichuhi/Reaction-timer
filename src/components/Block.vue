<template>
  <div class="block" v-if="showBlock" @click="stopTimer">click me</div>
</template>

<script>
import { onMounted } from "vue";

export default {
  props: ["delay"],
  data() {
    return {
      showBlock: false,
      timer: true,
      reactionTime: 0,
    };
  },
  mounted() {
    console.log("i am good at this");
    setTimeout(() => {
      this.showBlock = true;
      this.starTimer();
    }, this.delay);
  },
  methods: {
    starTimer() {
      this.timer = setInterval(() => {
        this.reactionTime += 10;
      });
    },
    stopTimer() {
      clearInterval(this.timer);
      console.log(this.reactionTime);
      this.$emit("end", this.reactionTime);
    },
    
  },
};
</script>

<style>
.block {
  width: 400px;
  border-radius: 20px;
  background: #afaf87;
  color: white;
  text-align: center;
  padding: 100px 0;
  margin: 40px auto;
}
</style>