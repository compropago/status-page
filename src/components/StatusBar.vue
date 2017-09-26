<template lang="html">
  <div :class="['bar ' + className]" @mouseover="showmodal = true" @mouseleave="showmodal = false">
    <div class="modal" v-if="showmodal">
      <div class="modal-date">{{date}}</div>
      <div class="modal-text">{{message}}</div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'StatusBar',
  props: ['className', 'date', 'message'],
  data() {
    return {
      showmodal: false,
    };
  },
};
</script>

<style>
.bar {
  background-color: red;
  height: 60px;
  width: 10px;
  position: relative;
}
.danger {
  background: #E14261
}
.warning {
  background: #F58620
}
.success {
  background: #45C6CC
}
.modal {
  background: #16325C;
  border-radius: 7px;
  color: white;
  padding: 1rem;
  min-width: 200px;
  max-width: 300px;
  max-height: 102px;
  position: absolute;
  right: 10px;
  top: -10rem;
  left: -2rem;
}
.modal::before {
  position: absolute;
  top: 99%;
  left: 1rem;
  content: '';
  border-left: 19px solid transparent;
  border-right: 19px solid transparent;
  border-top: 12.5px solid #16325C;
  width: 0px;
  height: 50px;

}
</style>
