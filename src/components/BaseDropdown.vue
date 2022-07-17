<template>
  <q-btn-dropdown flat class="text-capitalize" :label="label">
    <div class="row flex justify-between q-pa-md">
      <div class="column">
        <div class="text-h7 q-my-auto">{{ label }}</div>
      </div>
      <div class="column">
        <div class="text-right">
          <q-btn fab-mini small icon="close" flat />
        </div>
      </div>
    </div>

    <q-list bordered>
      <q-item clickable v-ripple v-for="(item, i) of items" :key="i">
        <q-item-section avatar>
          <q-img :src="item.image" />
        </q-item-section>

        <q-item-section>{{ item.link }}</q-item-section>
      </q-item>
    </q-list>
  </q-btn-dropdown>
</template>

<script setup>
const props = defineProps({
  label: {
    type: String,
    default: "Dropdown",
  },
  items: {
    type: Array,
    default: () => [],
  },
});
</script>

<style></style>
