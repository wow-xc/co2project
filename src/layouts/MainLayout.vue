<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-toolbar-title class="text-center">CO2project</q-toolbar-title>
      </q-toolbar>
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>
    <q-footer class="bg-white text-black ui">
      <!-- <q-toolbar> </q-toolbar> -->
      <q-tabs
        switch-indicator
        indicator-color="green"
        align="center"
        style="box-shadow: 0 5px 0 0 black"
      >
        <q-route-tab to="/introduce" label="웹소개" icon="description" />
        <q-route-tab to="/" label="홈" icon="home" />
        <q-route-tab to="/question" label="문의하기" icon="phone" />
      </q-tabs>
    </q-footer>
  </q-layout>
</template>

<script setup>
import { ref } from "vue";
</script>
