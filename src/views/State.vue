<template>
  <div :style="{ width: number + 'px' }" class="bar">
    <span>{{ number }}</span>
  </div>
</template>

<script>
export default {
  name: 'State',
  data() {
    return {
      number: 0
    }
  },
  methods: {
    randomNumber() {
      this.number = Math.floor(Math.random() * (800 - 0))
    }
  },
  created() {
    setInterval(this.randomNumber, 1500)
  }
}
</script>

<style scoped>
.bar {
  padding: 5px;
  background-color: #2c3e50;
  border: 1px #16c0b0 solid;
  min-width: 20px;
}
.bar span {
  color: white;
}
</style>
