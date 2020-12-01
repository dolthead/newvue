<template>
  <ion-app>
    <div v-if="initialized">
      <ion-router-outlet />
    </div>
  </ion-app>
</template>

<script lang="ts">
import { IonApp, IonRouterOutlet } from "@ionic/vue";
import { defineComponent } from "vue";
import useFirebaseAuth from "./userService";

export default defineComponent({
  name: "App",
  components: {
    IonApp,
    IonRouterOutlet,
  },
  setup() {
    const { initialized } = useFirebaseAuth();
    return {
      initialized,
    };
  },
});
</script>
