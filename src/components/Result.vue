<template>
  <p>Result is {{score}}ms</p>
  <div v-if="score<250">
      <p>you are to fast</p>
  </div>
  <div v-else-if="score>250 && score<500">
      <p>you are normal</p>
  </div>
  <div v-else>
      <p>you have to try more</p>
  </div>
</template>

<script>
export default {
    props:['score']
}
</script>

<style>

</style>