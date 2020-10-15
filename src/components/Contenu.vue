<template>
  <div class="container mt-5">
    <h1 class="mt-5 text-center">Forumaire</h1>
    <form action="" class="p-5">
      <div class="form-group">
        <label for="prenom">First Name</label>
        <input
          v-on:input="toggleResult"
          v-model.lazy="formData.prenom"
          type="text"
          id="prenom"
          class="form-control"
        />
      </div>
      <div class="form-group">
        <label for="txt">Your text</label>
        <textarea
          v-on:input="toggleResult"
          v-model="formData.texte"
          class="form-control"
          id="txt"
        ></textarea>
      </div>

      <h1>SelectBox</h1>

      <select
        name=""
        id="pays"
        class="form-control"
        v-model="formData.select"
        v-on:input="toggleResult"
      >
        <option
          v-for="(pays, indexPays) in formData.listePays"
          :key="indexPays"
          v-bind:value="pays"
          >{{ pays }}</option
        >
      </select>

      <h1 class="mt-3">Checkbox</h1>

      <div class="form-check">
        <input
          v-on:input="toggleResult"
          v-model="formData.checkFruit"
          type="checkbox"
          class="form-check-input"
          value="fraise"
          id="fraise"
        />
        <label for="fraise">Fraise</label>
      </div>

      <div class="form-check">
        <input
          v-on:input="toggleResult"
          v-model="formData.checkFruit"
          type="checkbox"
          class="form-check-input"
          value="pomme"
          id="pomme"
        />
        <label for="pomme">Pomme</label>
      </div>

      <div class="form-check">
        <input
          v-on:input="toggleResult"
          v-model="formData.checkFruit"
          type="checkbox"
          class="form-check-input"
          value="banane"
          id="banane"
        />
        <label for="banane">Banane</label>
      </div>

      <button v-on:click.prevent="envoiForm" class="btn btn-primary mt-3">
        Envoyer
      </button>
    </form>

    <div v-if="infoSubmit">
      <h2>Résultat</h2>

      <div class="card p-3">
        <p>Prénom : {{ formData.prenom }}</p>
        <p style="white-space: pre">Texte : {{ formData.texte }}</p>
        <br />
        <br />
        <h6>Résultat checkboxs</h6>
        <ul>
          <li v-for="(fruit, index) in formData.checkFruit" :key="index">
            {{ fruit }}
          </li>
        </ul>
        <h6>Le pays est :</h6>
        <p>{{ formData.select }}</p>
      </div>
    </div>
  </div>
</template>
<!---------------------------------------------------------------------------------------------------------------------------------------------------->
<script>
export default {
  name: "Contenu",
  data() {
    return {
      formData: {
        prenom: "",
        texte: "",
        checkFruit: [],
        select: "",
        listePays: [
          "Russie",
          "Angleterre",
          "Etat Unis",
          "Allemagne",
          "France",
          "Argentine",
        ],
      },
      infoSubmit: false,
    };
  },
  methods: {
    envoiForm: function() {
      this.infoSubmit = true;
    },
    toggleResult: function() {
      this.infoSubmit = false;
    },
  },
};
</script>

<!---------------------------------------------------------------------------------------------------------------------------------------------------->
<style scoped></style>
