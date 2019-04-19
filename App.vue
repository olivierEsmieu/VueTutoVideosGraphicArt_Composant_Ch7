<template>
  <div class="ui main container" id="app">
    <form-user v-model="user"> 
    <div slot="header">du texte en haut dans mon composant</div>
    <div slot="footer">du texte en bas de mon composant</div>
    </form-user>
    <pre>
  {{user}}
  </pre>
    <p>&nbsp;</p>

    <button v-if="!alert" @click="showAlert" class="ui button">Alerter</button>
    <message
      v-if="alert"
      :message="message"
      type="error"
      header="Attention"
      @close="hideAlert"
    >
    </message>
    <Counter :start="3"></Counter> <Counter></Counter>
  </div>
</template>

<script>
import Counter from "./Counter";
import FormUser from "./Formuser";
import Message from "./Message";
export default {
  directives: {},
  components: { Counter, Message, FormUser },
  data: function() {
    return {
      alert: false,
      user: {
        firstname: "Jean",
        lastname: "Valjan"
      }
    };
  },
  methods: {
    showAlert() {
      this.alert = true;
    },
    hideAlert() {
      this.alert = false;
    }
  }
};
</script>

<style scoped>
.ui.main.container {
  padding-top: 50px;
}
</style>
