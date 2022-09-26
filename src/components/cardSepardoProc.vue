<script>
export default {
  props: {
    procurado: {
      type: Object,
    },
  },
  mounted() {
    console.log(this.procurado);
  },
};
</script>
<template>
  <div class="img">
    <img
      class="imgproc"
      :src="procurado.images[0].original"
      onerror="this.src = 'https://cdn.discordapp.com/attachments/976322101818560562/1022715221099421736/silhueta-cinzenta-de-pessoa-anonima-com-ponto-interrogacao-sobre-fundo-branco-conceito-desconhecida-na-web-163956120.jpg'"
    />
  </div>
  <div class="infos">
    <h2 class="name">{{ procurado.title }}</h2>
    <p>{{ procurado.description }}</p>
  </div>
</template>
<style>

.infos h2 {
  width: 80%;
  color: #B68d4A;
}
</style>
