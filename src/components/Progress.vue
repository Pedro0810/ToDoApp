<template>
  <div class="progress">
    <span class="value">{{ progress }}%</span>
    <div class="bar" :style="{width: progress + '%'}"></div>
  </div>
</template>

<script>
export default {
  props: {
    progress: {
      type: Number,
      default: 0
    }
  }
}
</script>

<style>
.progress {
  position: relative;
  width: 80%;
  border: 1px solid #FFF;
  border-radius: 8px;
  margin-bottom: 15px;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.value {
  z-index: 1;
  font-size: 1.5rem;
}
.bar {
  position: absolute;
  border-radius: 8px;
  height: 100%;
  background-color: #4CAF50;
  align-self: flex-start;
}
</style>