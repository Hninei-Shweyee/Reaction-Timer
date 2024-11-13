<template>
  <p>Result is {{score}} ms </p>
  <div v-if="score<250">
    <p>WoW! you are so fast</p>
  </div>
  <div v-else-if="score>250 && score<500">
    <p>You are normal</p>
  </div>
  <div v-else>
    <p>Your are too slow! try to be fast!</p>
  </div>
</template>
<script>
export default {
    props:['score']
}
</script>

<style>

</style>