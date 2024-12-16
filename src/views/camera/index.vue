<template>
    <ion-page>
      <ion-header>
        <ion-toolbar color="primary">
          <ion-buttons slot="start">
            <ion-back-button></ion-back-button>
          </ion-buttons>
          <ion-title> CAMERA </ion-title>
        </ion-toolbar>
      </ion-header>
      <ion-content>
           <div class="p-3">
                <button class="btn btn-secondary btn-lg w-100" @click="takePhoto()"> Take Photo </button>
           </div>
        </ion-content>
    </ion-page>
  </template>
  
  <script lang="ts">
  import { defineComponent } from 'vue';
  import { menu, home, person } from 'ionicons/icons';
  import { Camera, CameraResultType } from '@capacitor/camera';
  
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
    name: 'GPSscreen',
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
    methods: {
       async takePhoto() {
                const image = await Camera.getPhoto({
            quality: 90,
            allowEditing: true,
            resultType: CameraResultType.Uri
        });
        var imageUrl = image.webPath;
      
            }
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