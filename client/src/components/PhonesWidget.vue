<template>
  <v-menu :close-on-content-click="false">
    <template v-slot:activator="{ props }">
      <v-btn color="primary" v-bind="props"
        >ТЕЛЕФОНІЯ <TelephonSettings
      /></v-btn>
    </template>

    <v-list>
      <v-list-item v-for="(item, index) in items" :key="index">
        <v-list-item-title>{{ item.title }}</v-list-item-title>
      </v-list-item>
    </v-list>
  </v-menu>
</template>
<script>
import LastInteractions from "./journal/LastInteractions.vue";
import MissedCalls from "./journal/MissedCalls.vue";
import CallHistory from "./journal/CallHistory.vue";
import TelephonSettings from "./telephonSettings/TelephonSettings.vue";
export default {
  components: {
    LastInteractions,
    MissedCalls,
    CallHistory,
    TelephonSettings,
  },
  data: () => ({
    items: [
      { title: "ОСТАННІ ВЗАЄМОДІЇ", image: "../assets/open.svg" },
      { component: LastInteractions },
      { title: "ПРОПУЩЕНІ ДЗВІНКИ" },
      { component: MissedCalls },
      { title: "ІСТОРІЯ ДЗВІНКІВ" },
      { component: CallHistory },
    ],
  }),
};
</script>
