<template>
  <div id="usercard">
    <p>Nom: {{ name }}</p>
    <ion-button color="danger" @click="decrement()">-</ion-button>
    <p>Score: {{ score }}</p>
    <ion-button color="primary" @click="increment()">+</ion-button>
  </div>
</template>

<script>
import {defineComponent, ref} from "vue";
import {IonButton, } from "@ionic/vue";

export default defineComponent({
  name: "UserCard.vue",
  components: { IonButton, },
  props: {
    name: String,
    score: Number
  },

  setup() {
    let score = ref(0)

    const decrement = () => {
      score.value--
    }

    const increment = () => {
      score.value++
    }

    // eslint-disable-next-line vue/no-dupe-keys
    return {score, decrement, increment}
  }
});

</script>

<style scoped lang="scss">
#usercard {
  border: 1px solid black;
  border-radius: 5px;

  p:first-child {
    color: red;
  }
}

ion-button {
  display:inline-block;
  border: #0088FFFF 1px solid;
  margin:2px;
  font-size:24px;
  cursor:pointer;
  width:50px;
  height:50px;
  border-radius:100%;
}

</style>