<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-toolbar-title> Allegro </q-toolbar-title>
        <q-btn color="secondary">Create</q-btn>
        <BaseDropdown
          label="Workspaces"
          :items="workspaces"
          class="q-mx-sm"
        ></BaseDropdown>
        <BaseDropdown
          label="Recent"
          :items="workspaces"
          class="q-mx-sm"
        ></BaseDropdown>

        <q-input
          dark
          dense
          standout
          v-model="text"
          label="Search"
          class="q-mx-sm"
        >
          <template v-slot:append>
            <q-icon v-if="text === ''" name="search" />
            <q-icon
              v-else
              name="clear"
              class="cursor-pointer"
              @click="text = ''"
            />
          </template>
        </q-input>

        <div>v0.0.1</div>
      </q-toolbar>
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script setup>
import BaseDropdown from "../components/BaseDropdown.vue";

const workspaces = [
  {
    link: "Workspace 1",
    image: "https://picsum.photos/200/300",
  },
  {
    link: "Workspace 2",
    image: "https://picsum.photos/200/300",
  },
  {
    link: "Workspace 3",
    image: "https://picsum.photos/200/300",
  },
];
</script>
