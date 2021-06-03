<template>
  <form @submit.prevent="translateIt" class="well">
    <textarea
      v-model="translateText"
      cols="30"
      rows="5"
      class="form-control"
      placeholder="Çevirmek istediğiniz kelime/cümle yazınız."
    ></textarea>
    <select v-model="translateTo" class="form-control">
      <option>1</option>
    </select>
    <br />
    <div class="text-left">
      <strong>Tespit Edilen Dil : </strong>
    </div>
    <br />
    <button type="submit" class="btn btn-primary btn-block">
      Çevir Gelsin!
    </button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      translateText: '',
      translateTo: '',
    }
  },
  methods: {
    translateIt() {
      alert(this.translateText)
      alert(this.translateTo)
    },
  },
}
</script>
<style></style>
