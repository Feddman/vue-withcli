

<template>
  <div class="root" :style="{background: background}">
      <button @click="increment()" class="button is-primary">+</button>
      <button @click="decrement()" class="button is-primary">-</button>
      <div class="number">{{ number }} </div>

  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      msg: 'Welkom to my amazing vue app',
      number: 0,
      background: "red"
    }
  },
  methods: {

    increment: function() {
      this.number++;
    },

    decrement: function() {
      if (!this.number < 1)
      {
          this.number--;
      }
    }

  },

  watch: {
    number: function() {
      let backgrounds = ['red', 'green', 'orange', 'yellow', 'purple'];
      this.background = backgrounds[Math.floor( Math.random() * backgrounds.length )];
    }
  }


}
</script>

<style lang="scss">
  @import '~bulma/bulma';
  .number {
    font-size: 4rem;
  }


</style>
