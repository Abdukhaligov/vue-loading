<template>
  <div class="bb" style="background: blue">
    asd
  </div>
</template>

<script>

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  $anime-time: 4s;

  $box-size: 200px;
  $clip-distance: 0.5;
  $clip-size: $box-size * (1 + $clip-distance * 2);
  $clip-size-width: $box-size * (1 + $clip-distance * 2) + 200;
  $path-width: 2px;

  $main-color: red;

  %full-fill {
    position: absolute;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
  }

  .bb {
    @extend %full-fill;
    width: $box-size;
    height: $box-size;
    margin: auto;
    color: $main-color;
    &::after {
      @extend %full-fill;
      content: '';
      z-index: -1;
      margin: -1 * $clip-distance * 100%;
      box-shadow: inset 0 0 0 $path-width;
      animation: clipMe $anime-time linear infinite;
    }

    &:hover {
      &::after,
      &::before {
        background-color: rgba(#f00, .3);
      }
    }
  }

  @keyframes clipMe {
    0%, 100% { clip: rect(0px, $clip-size, $path-width, 0px); }
    25% { clip: rect(0px, $path-width, $clip-size, 0px); }
    50% { clip: rect($clip-size - $path-width, $clip-size, $clip-size, 0px); }
    75% { clip: rect(0px, $clip-size, $clip-size, $clip-size - $path-width); }
  }


</style>
