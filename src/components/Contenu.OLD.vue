<template>
  <div class="container mt-5">
    <h1 class="mt-5">Forumaire</h1>
    <form action="">
      <div class="form-group">
        <label for="prenom">First Name</label>
        <input v-model="prenom" type="text" id="prenom" class="form-control" />
      </div>
      <div class="form-group">
        <label for="txt">Your text</label>
        <textarea v-model="texte" class="form-control" id="txt"></textarea>
      </div>
      <h2>Résultat</h2>
      <div class="card p-3">
        <p>Prénom : {{ prenom }}</p>
        <p>Texte : {{ texte }}</p>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: "Contenu",
  data() {
    return {
      prenom: "",
      texte: "",
    };
  },
  methods: {},
};
</script>

<style scoped></style>
