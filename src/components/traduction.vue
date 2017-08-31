<template>
  <div id="traduction">
  <p>{{ someData }}</p>
  </div>
</template>

<script>
export default {
  name: 'traduction',
  props: ['someData']

}
</script>

<style scoped>
#traduction {
	width: 50%;
	height: 10em;
	border: 1px solid #68A172;
	border-radius: 5px;
	margin: auto;
	margin-top: 2em;
}
</style>
