<template>
  <div id="texte">
    <form v-on:submit.prevent="traduire">
      <input type="text" v-model="texte" placeholder="entrez le texte à traduire">
      <select v-model="langue">
        <option value="en">Anglais</option>
        <option value="es">Espagnol</option>
        <option value="nl">Allemand</option>
        <option value="ar">Arabe</option>
      </select>
      <button type="submit">Traduire</button>
    </form>
  </div>
</template>

<script>
export default {
  name: 'textatraduire',
  data () {
    return {
      texte: "",
      langue: "en"
    }
  },

  methods: {
    traduire() {
      this.$emit('traduire', this.texte, this.langue)
    }
  }
}
</script>

<style scoped>

</style>
