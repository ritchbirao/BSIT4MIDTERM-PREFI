<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-buttons slot="start">
          <ion-back-button></ion-back-button>
        </ion-buttons>
        <ion-title class="bg-warning"> Swiper </ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content>
      <swiper :slides-per-view="1" :space-between="50" @swiper="onSwiper">
        <swiper-slide>
          <img
            class="banner"
            src="https://tse2.mm.bing.net/th?id=OIP.ubsqQ22Vs06H2mgb8PWZYwHaEK&pid=Api&P=0&h=220"
            alt="image 1"
          />
        </swiper-slide>
        <swiper-slide>
          <img
            class="banner"
            src="https://tse4.mm.bing.net/th?id=OIP.MH4A7iuQYFttumJYA9IO7QHaEK&pid=Api&P=0&h=220"
            alt="image 2"
          />
        </swiper-slide>
        <swiper-slide>
          <img
            class="banner"
            src="https://tse3.mm.bing.net/th?id=OIP.ftKvvD0pJ3TsiYptglmMBAHaEK&pid=Api&P=0&h=220"
            alt="image 3"
          />
        </swiper-slide>
      </swiper>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { menu, home, person } from 'ionicons/icons';
import { Swiper, SwiperSlide } from 'swiper/vue';
import 'swiper/css';

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
  name: 'swiperScreen',
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
    Swiper,
    SwiperSlide,
  },
  data() {
    return {
      swiper: {} as any,
    };
  },
  methods: {
    async onSwiper(event: any) {
      this.swiper = event;
    },
  },
  setup() {
    return {
      menu,
      home,
      person,
    };
  },
});
</script>

<style scoped>
.banner {
  width: 100vw;
  height: 260px;
  object-fit: cover;
  object-position: center;
}
</style>
