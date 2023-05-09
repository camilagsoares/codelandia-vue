<template>
  <div class="card">
    <!-- <div class="div">noticias</div> -->
    <!-- <div class="cardwhite">{{ mensagem }}</div> -->
    <div class="cardwhite" v-for="post in posts" :key="post.id">
      {{ post.titulo }}
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      titulo: "Olá Vue.js 2!",
      mensagem: "",
      posts: ""
    };
  },
  methods: {
    fazerRequisicao() {
      axios
        .get("https://60d94dabeec56d00174776a2.mockapi.io/api/v1/post")
        .then((response) => {
          console.log(response.data);
          this.posts = JSON.parse(response.data[0].titulo);
        //   this.posts = response.data;
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
  created() {
    this.fazerRequisicao();
    console.log("oi");
  },
};
</script>

<style scoped>
.card {
  display: flex;
  align-items: center;
  justify-content: center;

  /* p{
    margin: 15px;

&.description{
    font-size: 18px;
    color: #717171;
    font-weight: 300;
} */

  /* ::selection{
    background-color: #448EDE;
    color: white;

} */
}
.cardwhite {
  background-color: white;
  box-shadow: 1px 1px 1px 1px #dddfde;
  width: 900px;
  height: 195px;
  margin: 10px;
  border-radius: 9px;
  position: relative;
  top: 3vw;
  font-family: "Lexend Deca";
  color: #1a202c;
  font-size: 26px;
}

.separate {
  display: flex;
  justify-content: space-between;
}
</style>
