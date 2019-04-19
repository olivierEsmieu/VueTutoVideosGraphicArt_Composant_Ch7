<template>
  <div class="ui main container">
    <p><slot name="header"></slot></p>
    <form class="ui form" @submit.prevent="save">
      <div class="field">
        <label for="">Prénom</label>
        <input type="text" v-model="user.firstname" />
      </div>
      <div class="field">
        <label for="">Nom</label> <input type="text" v-model="user.lastname" />
      </div>
      <button class="ui button" type="submit">Valide</button>
    </form>
     <p><slot name="footer"></slot></p>
  </div>
</template>

<script>
export default {
  props: { value: { type: Object } },
  data() {
    return { user: { ...this.value } };
  },
  mounted: function() {},
  computed: {},
  methods: {
    save() {
      this.$emit("input", this.user);
    }
  }
};
</script>

<style scoped>
.ui.main.container {
  padding-top: 5px;
}
</style>
