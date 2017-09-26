<template>
  <div :class="[className, 'StatusHeader']">
    <div class="StatusHeader-left">
      <span class="StatusHeader-icon">{{icon}}</span>
      <span class="StatusHeader-title">{{title}}</span>
    </div>
    <span class="StatusHeader-time">{{status}}</span>
  </div>
</template>

<script>
export default {
  name: 'StatusHeader',
  props: ['icon', 'title', 'status', 'className'],
};
</script>

<style>
  .StatusHeader {
    align-items: center;
    color: white;
    display: flex;
    justify-content: space-between;
    height: 60px;
    padding: 0 1rem;
  }
  .success {
    background-color: #45C6CC;
  }
  .warning {
    background-color: #F58620;
  }
  .danger {
    background-color: #E14261;
  }
</style>
