<script>
import axios from "axios";

export default {
  data() {
    return {
      title: "Lista carte",
      characters: [],
    };
  },
  created() {
    axios
      .get("https://db.ygoprodeck.com/api/v7/cardinfo.php")
      .then((response) => {
        this.characters = response.data.data.slice(0, 18);
      });
  },
};
</script>
<template>
  <div class="container">
    <h1>{{ title }}</h1>
    <div class="row">
      <div class="col-2 mb-3" v-for="(card, index) in characters" :key="index">
        <div class="card">
          <img
            :src="card.card_images[0].image_url"
            class="card-img-top"
            alt="Card Image"
          />
          <div class="card-body">
            <h5 class="card-title">{{ card.name }}</h5>
            <p class="card-text">Type: {{ card.type }}</p>

            <!-- Altre informazioni sulla carta -->
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss"></style>
