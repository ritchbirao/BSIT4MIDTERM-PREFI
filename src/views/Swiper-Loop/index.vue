<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-buttons slot="start">
          <ion-back-button></ion-back-button>
        </ion-buttons>
        <ion-title class="bg-light"> Loop </ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content>
      <swiper :slides-per-view="1" :space-between="50" @swiper="onSwiper">
        <swiper-slide v-for="(banner, i) in banners" :key="i">
          <img class="banner" :src="banner" />
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
  name: 'swiperloopScreen',
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
      banners: [
        'https://tse3.mm.bing.net/th?id=OIP.ftKvvD0pJ3TsiYptglmMBAHaEK&pid=Api&P=0&h=220',
        'https://tse3.mm.bing.net/th?id=OIP.QlVV428DV5GNiXavdfu3IQHaEK&pid=Api&P=0&h=220',
        'https://tse2.mm.bing.net/th?id=OIP.dylOjmjeD3yYPHDPErwT8AHaEK&pid=Api&P=0&h=220',
        'https://tse2.mm.bing.net/th?id=OIP.ubsqQ22Vs06H2mgb8PWZYwHaEK&pid=Api&P=0&h=220',
        'https://tse1.mm.bing.net/th?id=OIP.JnrlMePHqROixPeCfwG1BwHaEK&pid=Api&P=0&h=220',
        'https://tse2.mm.bing.net/th?id=OIP.ERGRA2AINRaqfzEXh1qv9AHaDt&pid=Api&P=0&h=220  ',
      ],
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
