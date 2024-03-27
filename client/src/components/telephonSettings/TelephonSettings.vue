<template>
  <v-menu :close-on-content-click="false" location="end">
    <template v-slot:activator="{ props }">
      <v-btn color="primary" v-bind="props">
        <img src="../../assets/telephonSettings.svg" />
      </v-btn>
    </template>
    <v-list>
      <v-list-item v-for="(item, index) in items" :key="index">
        <v-list-item-avatar>
          <img :src="item.image" alt="Изображение" />
        </v-list-item-avatar>
        <v-list-item-title>{{ item.title }}</v-list-item-title>
      </v-list-item>
    </v-list>
  </v-menu>
</template>
<script>
import PopupConnectedDevices from "./settingsPopup/PopupConnectedDevices.vue";
import PopupTabNames from "./settingsPopup/PopupTabNames.vue";
import PopupPeriodsAndIntervals from "./settingsPopup/PopupPeriodsAndIntervals.vue";

export default {
  components: {
    PopupConnectedDevices,
    PopupTabNames,
    PopupPeriodsAndIntervals,
  },
  data: () => ({
    items: [
      { title: "ПРИЄДНАНІ ПРИСТРОЇ", component: PopupConnectedDevices },
      { title: "НАЙМЕНУВАННЯ ВКЛАДОК", component: PopupTabNames },
      { title: "ПЕРІОДИ ТА ІНТЕРВАЛИ", component: PopupPeriodsAndIntervals },
    ],
  }),
};
</script>
