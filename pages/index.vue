<template>
  <div id="index-wrap">
    <div
      @click="pop"
      class="pop-btn"
    >팝업</div>
    <!-- <transition name="slide-fade"> -->
        <Pop1
          v-if="checkParam"
        />
    <!-- </transition> -->
        <!-- v-if="Object.keys(this.$route.params).length > 0"
        :class="Object.keys(this.$route.params).length > 0 ? 'ani' : ''" -->
  </div>
</template>

<script>

import { Route } from 'vue-router';
import Pop1 from '../components/Pop1.vue';
import eventBus from '../plugins/eventBus.js';

export default {
  components: {
    Pop1,
  },
  data() {
    return {
      pop1: '',
      checkParam: Object.keys(this.$route.params).length > 0 ? true : setTimeout(()=>{false},500),
      test: false,
    }
  },
  methods: {
    pop() {
      this.pop1 = 'pop1';
      this.$router.push(`/${this.pop1}`);
    }
  },
  created() {
    // setTimeout(() => {
    //   this.test = true;
    // }, 1000);
    if (Object.keys(this.$route.params).length > 0) {
      this.checkParam = true;
    }
    
  },
}
</script>



<style>
  #index-wrap{width: 100%;height: 100%;background-color: #e3e3e3;overflow: hidden;}
  .pop-btn{width: 80px;height: 42px;background-color: rgb(248, 130, 52);position: absolute;bottom: 10%;left: calc(50% - 40px);color: #e3e3e3;text-align: center;line-height: 42px;cursor: pointer;}
 

</style>

