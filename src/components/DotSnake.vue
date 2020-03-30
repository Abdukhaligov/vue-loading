<template>
  <div class="hello">
    <div class="wrapper">
      <div v-for="i in 50" :key="i" class="dot">

      </div>
    </div>
  </div>
</template>

<script>

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  $count    : 50; // how many dots?
  $duration : 25; // for how long (in percent) the animation should stay at opacity: 1
  $range    : 100 - $duration - 1;

  .wrapper { display: flex; width: 100%; padding: 50px; }
  .dot { display: block; width: 5px; height: 5px; background: #000; border-radius: 50%; margin: 3px}

  @for $i from 1 through $count {
    .dot:nth-child(#{$i}) { animation: blink-#{$i} 2s infinite linear; }
    @keyframes blink-#{$i} {
  0% { opacity: 0.1; }
  #{$i*($range/$count)}% { opacity: 0.1; }
  #{$i*($range/$count) + 1}% { opacity: 1; }
  #{$i*($range/$count) + $duration}% { opacity: 1; }
  #{$i*($range/$count) + $duration + 1}% { opacity: 0.1; }
  100% { opacity: 0.1; }
  }
  }

</style>
