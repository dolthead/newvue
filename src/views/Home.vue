<template>
  <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar color="primary">
        <ion-title>{{ title }}</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">{{ title }}</ion-title>
        </ion-toolbar>
      </ion-header>
      <ion-fab vertical="top" horizontal="end" slot="fixed">
        <ion-fab-button color="secondary" @click="doSomething">
          <!-- <ion-icon :icon="icons.add"></ion-icon> -->
          <ion-icon :icon="add"></ion-icon>
        </ion-fab-button>
      </ion-fab>
      <ion-list>
        <ion-item v-for="(x, $index) in 20" :key="$index" lines="full">
          test {{ x }}
        </ion-item>
      </ion-list>
      <section>
        <p class="bottom-section">
          <ion-button expand="block"> Hello </ion-button>
        </p>
      </section>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
// import * as icons from "ionicons/icons";
import { add } from "ionicons/icons";
import {
  IonContent,
  IonHeader,
  IonPage,
  IonTitle,
  IonToolbar,
  IonList,
  IonItem,
  IonFab,
  IonFabButton,
  IonButton,
  IonIcon,
} from "@ionic/vue";
import { defineComponent, ref } from "vue";

export default defineComponent({
  name: "Home",
  components: {
    IonContent,
    IonHeader,
    IonPage,
    IonTitle,
    IonToolbar,
    IonList,
    IonItem,
    IonFab,
    IonFabButton,
    IonButton,
    IonIcon,
  },
  setup() {
    const title = ref("Vue 3 + Ionic 5");
    const doSomething = () => (title.value = "Reactively updated");
    return {
      title,
      // icons,
      add,
      doSomething,
    };
  },
});
</script>

<style scoped>
.bottom-section {
  padding: 10px;
  background-image: radial-gradient(#ff8a00, #e52e71) !important;
}
</style>