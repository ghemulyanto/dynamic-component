<template>
  <v-app>
    <v-container>
      <v-text-field
        v-for="(text,index) in texts"
        :key="index"
        placeholder="Text"
        v-model="text.name"
        outlined
        :append-outer-icon="'mdi-close-circle-outline'"
        @click:append-outer="deleteComponent(index)"
      ></v-text-field>

      <v-btn v-on:click="addComponent" color="indigo" text outlined>Add</v-btn>
    </v-container>
  </v-app>
</template>

<script>
export default {
  name: "App",

  data() {
    return {
      texts: [
        {
          name: ""
        }
      ]
    };
  },
  methods: {
    addComponent() {
      this.texts.push({ name: "" });
    },
    deleteComponent(index) {
      this.texts.splice(index, 1);
    }
  }
};
</script>
 