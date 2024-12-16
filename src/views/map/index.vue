<template>
  <ion-page>
    <ion-header>
      <ion-toolbar color="primary">
        <ion-buttons slot="start">
          <ion-back-button></ion-back-button>
        </ion-buttons>
        <ion-title> Map </ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content>
      <div id="map"></div>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">

/**
* API key: AIzaSyA7nyAevnZcR1GncVAydyO9Nkip0JCBnb8
*/

import { defineComponent } from 'vue';
import { menu, home, person } from 'ionicons/icons';
import { GoogleMap } from '@capacitor/google-maps';

import {
  IonBackButton,
  IonButtons,
  IonToolbar,
  IonTitle,
  IonHeader,
  IonPage,
  IonContent,
  IonIcon,
  IonRouterOutlet,
} from '@ionic/vue';

export default defineComponent({
  name: 'mapScreen',
  components: {
    IonBackButton,
    IonButtons,
    IonToolbar,
    IonTitle,
    IonHeader,
    IonPage,
    IonContent,
    IonIcon,
    IonRouterOutlet,
  },
  data() {
    return {
      apiKey: 'AIzaSyA7nyAevnZcR1GncVAydyO9Nkip0JCBnb8',
    };
  },
  methods: {
    async initMap() {
      const mapRef = document.getElementById('map') as HTMLElement;

      const newMap = await GoogleMap.create({
        id: 'my-map',
        element: mapRef,
        apiKey: this.apiKey,
        config: {
          center: {
              lat: 10.2264417,
              lng: 123.7624066,
          },
          zoom: 21,
        },
      });
    },
  },
  setup() {
    return {
      menu,
      home,
      person,
    };
  },
  async mounted() {
    this.initMap();
  },
});
</script>

<style scoped>
   #map {
      display: inline-block;
      width: 100vw;
      height: 100vh;
    }
</style>