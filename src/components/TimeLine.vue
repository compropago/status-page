<template>
  <div class="timeline">
    <span class="data data-left">{{startDay}}</span>
    <div class="line"></div>
    <span>{{upTime}}</span>
    <div class="line"></div>
    <span class="data data-rigth">{{endDay}}</span>
  </div>
</template>

<script>
export default {
  name: 'TimeLine',
  props: ['startDay', 'endDay', 'upTime'],
};
</script>

<style>
.timeline {
  color: #939EB3;
  display: flex;
  justify-content: space-between;
  margin-top: 1.5rem
}
.data {
  position: relative;
}
.data-rigth::before {
  right: 4px;
}
.data-left::before {
  left: 3px;
}
.data::before {
  content: '|';
  position: absolute;
  top: -21px;
}
.line{
  width: 39%;
  background: #939EB3;
  margin: 0 auto;
  position: relative;
  top: 12px;
  height: 1px;
}
</style>
