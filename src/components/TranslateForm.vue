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
import axios from 'axios'
export default {
  data() {
    return {
      translateText: '',
      translateTo: '',
    }
  },
  /* API key:
  tmsl.1.120180919T140412Z.20a6cc3cb2b92135.859b224f09389c0502296ae695358c150a77804c
  */
  methods: {
    translateIt() {
      let url =
        'https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20180919T140412Z.20a6cc3cb2b92135.859b224f09389c0502296ae695358c150a77804c&text=' +
        this.translateText +
        '&lang=en'
      axios
        .get(url)
        .then((response) => {
          console.log(response)
        })
        .catch((e) => console.log(e))
      //url = https://translate.yandex.net/api/v1.5/tr.json/translate
    },
  },
}
</script>
<style></style>
