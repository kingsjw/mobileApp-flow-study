<template>
  <div
    id="pop1"
    :class="Object.keys(this.$route.params).length > 0 ? 'open' : 'back'"
  >
    <h1>팝업 페이지1</h1>
    <div
      @click="back"
      class="pop-btn"
    >뒤로가기</div>    
  </div>
</template>
<script>

import eventBus from '../plugins/eventBus.js';

export default {
  methods: {
    back() {
      history.back();
    }
  }
}
</script>

<style>
  #pop1{width: 100%;height: 100%;background-color: #2548db;color: #fff; transition: transform 0.5s ease;}
  .open{animation-name: ani;animation-duration: 0.5s;transform: translateX(0);}
  .back{animation-name: close;animation-duration: 0.5s;transform: translateX(100%);}
  @keyframes ani {
    0%{transform: translateX(100%);}
    100%{transform: translateX(0%);}
  }
  @keyframes close {
    0%{transform: translateX(0);}
    100%{transform: translateX(100%);}
  }
</style>
<style scoped>
  .pop-btn{background-color: rgb(241, 64, 167);}
</style>


