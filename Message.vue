<template>
  <div class="ui main container">
    <div class="ui message" :class="type">
      <i @click.prevent="close" class="ui icon close" />
      <div class="ui header">{{ header }}</div>
      {{ message }}
    </div>
  </div>
</template>

<script>
export default {
  props: {
    message: { type: String, default: "message" },
    header: { type: String, default: "header" },
    type: { type: String, default: "success" }
  },
  data: function() {
    return {};
  },
  mounted: function() {},
  computed: {},
  methods: {
    close() {
      this.$emit("close");
    }
  }
};
</script>

<style scoped>
.ui.main.container {
  padding-top: 5px;
}
</style>
