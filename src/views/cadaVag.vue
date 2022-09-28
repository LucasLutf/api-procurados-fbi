<script>
import axios from "axios";
import { onBeforeMount } from "vue";

// import { onBeforeMount, reactive } from "vue";

import cardSepardoProc from "../components/cardSepardoProc.vue";

export default {
  components: { cardSepardoProc },
  data() {
    return {
      data: [],
    };
  },
  async created() {
    const { data } = await axios.get(
      `https://api.fbi.gov/@wanted-person/${this.$route.params.id}`
    );
    this.data = data;
  },
  // props: {
  //     procurado: {
  //         type: Object
  //     }
  // }
};
</script>
<template>
  <div class="cardseparado">
    <cardSepardoProc :procurado="data" />
  </div>
</template>
<style>
.txtprin {
  display: flex;
  align-items: center;
  justify-content: center;
  margin-top: 1.5%;
  font-family: Arial, Helvetica, sans-serif;
  font-weight: bold;
  color: #0a0a12;
  font-size: 2em;
  margin-right: 14.5%;
}

.categorias {
  display: flex;
  align-items: center;
  justify-content: center;
}

.categorias span {
  margin: 0 4%;
}

.previa,
.cardseparado {
  display: flex;
  padding: 5%;
  height: 60vh;
  margin-left: 10%;
}

.infos {
  width: 24%;
  font-family: Impact, Haettenschweiler, "Arial Narrow Bold", sans-serif;
  border: solid 1px rgb(226, 166, 0);
  width: 50%;
  height: 80%;
  border-radius: 24px;
  padding: 24px;
  background-color: #131324;
  color: #fff;
  box-shadow: 0 0 20px 0 rgba(0, 0, 0, 0.644);
  border-style: outset;
}
.img {
  margin-right: -120px;
}
.previa img,
.cardseparado img {
  width: 60%;
  border-radius: 20px;
  box-shadow: 0 0 15px 0 #000;

}
</style>
