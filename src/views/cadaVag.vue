<script>
import axios from "axios";

// import { onBeforeMount, reactive } from "vue";

import cardSepardoProc from '../components/cardSepardoProc.vue'

export default {
    components: { cardSepardoProc },
    data() {
        return {
            data: []
        }
    },
    async mounted() {
        const { data } = await axios.get(`https://api.fbi.gov/@wanted-person/${this.$route.params.id}`)
        this.data = data
    },
    props: {
        procurado: {
            type: Object
        }
    }
}

</script>
<template>
    <div class="main">
        <div class="lista">

            <h2 class="txtprin">Mais Procurados</h2>
            <hr>
            <div class="categorias">
                <span>Terrorismo</span>
                <span>Fugitivos</span>
                <span>Desaparecidos</span>
            </div>
        </div>
    </div>
    <cardSepardoProc :procurado="data" />
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

.previa {
    display: flex;
    padding: 5%;
    margin-left: 10%;
}

.infos {
    width: 30%;
    font-family: Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
    margin-left: 80px;
    margin-right: 240px;
}

.previa img {
    margin-left: 20px;
    width: 90%;
    border-radius: 20px;
    box-shadow: 0 0 10px 0 #000;
}
</style>