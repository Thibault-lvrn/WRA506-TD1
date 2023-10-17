<script setup>
defineProps({
  msg: {
    type: String,
    required: true
  }
})
</script>

<template>
  <div class="greetings">
    <h2 class="green">{{ msg }}</h2>
  </div>
</template>

<style scoped>
.greetings h2 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h2{
    text-align: left;
  }
}
</style>
