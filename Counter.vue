<template>
  <div class="ui main container">
    <button @click="increment">{{ total }}</button>
  </div>
</template>

<script>
export default {
  props: {
    start: { type: Number, default: 0 }
  },
  data: function() {
    return {
      count: 0
    };
  },
  mounted: function() {},
  computed: {
    total: {
      get: function() {
        return this.start + this.count;
      }
    }
  },
  methods: {
    increment: function() {
      this.count = this.count + 1;
    }
  }
};
</script>

<style scoped>
.ui.main.container {
  padding-top: 50px;
}
</style>
