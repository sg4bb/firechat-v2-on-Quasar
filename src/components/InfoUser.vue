<script setup>
import { inject} from "vue";

const userGoogle = inject("userGoogle");
</script>

<template>
  <q-scroll-area
    style="
      height: calc(100% - 150px);
      margin-top: 150px;
      border-right: 1px solid #ddd;
    "
  >
    <q-list padding>
      <q-item clickable v-ripple to="/">
        <q-item-section avatar>
          <q-icon name="mdi-chat" />
        </q-item-section>

        <q-item-section> Chat </q-item-section>
      </q-item>
    </q-list>
  </q-scroll-area>

  <q-img
    class="absolute-top"
    src="https://cdn.quasar.dev/img/material.png"
    style="height: 150px"
  >
    <div class="absolute-bottom bg-transparent">
      <q-avatar size="56px" class="q-mb-sm">
        <img :src="userGoogle.photoURL" />
      </q-avatar>
      <div class="text-weight-bold">{{ userGoogle.displayName }}</div>
      <div>{{ userGoogle.email }}</div>
    </div>
  </q-img>
</template>
