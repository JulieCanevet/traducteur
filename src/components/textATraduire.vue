<template>
  <div id="texte">
    <h1>Traducteur</h1>
    <form v-on:submit.prevent="traduire">
      <input type="text" v-model="texte" placeholder="entrez le texte à traduire">
      <br>
      <select v-model="langue">
        <option value="en">Anglais</option>
        <option value="es">Espagnol</option>
        <option value="de">Allemand</option>
        <option value="ar">Arabe</option>
        <option value="ru">Russe</option>
        <option value="ja">Japonais</option>
        <option value="eo">Esperanto</option>
        <option value="uk">Ukrainien</option>
        <option value="pt">Portaugais</option>
        <option value="mk">Macedonien</option>
        <option value="af">Africain</option>
        <option value="bg">Bulgare</option>
        <option value="vi">Vietnamien</option>
        <option value="zh">Chinois</option>
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

input {
  width: 50%;
  height: 3em;
  margin-bottom: 2em;
  border-radius: 6px;
}
h1 {
  color: #B8D134;
  letter-spacing: .2em;
}
</style>
