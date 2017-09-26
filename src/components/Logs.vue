<template>
  <div class="Logs">
    <div class="Logs-header">
      <span class="Logs-detail">Posted {{detail}}</span>
      <span class="Logs-title">{{title}}</span>
      <span>-</span>
      <span :class="['Logs-status', status]">{{status}}</span>
    </div>
    <span class="Logs-info">{{info}}</span>
  </div>
</template>

<script>
export default {
  name: 'Logs',
  props: ['detail', 'title', 'status', 'info'],
};
</script>

<style>
  .Logs {
    border-top: 1px solid #DDE6EF;
    padding: 1.5rem 0;
    text-align: left
  }
  .Logs-detail {
    color: #72859F;
    font-size: 12px;
    margin-bottom: 5px;
    display: block;
  }
  .Logs-title {
    color: #4782BB;
  }
  .Resolved {
    color: #45C6CC;
  }
  .Logs-header {
    margin-bottom: 1rem;
  }
</style>
