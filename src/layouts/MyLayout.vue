<template>
  <q-layout view="lHh Lpr lFf">
    <q-header class="bg-indigo-1">
      <q-toolbar color="grey-9">
        <q-btn flat @click="drawer = !drawer" round dense icon="menu" color="grey-8"></q-btn>
        <q-toolbar-title>
          <span class="text-grey-9">GSI</span>
          <span class="text-grey-6 q-ml-sm">Health</span>
        </q-toolbar-title>
        <!-- <q-btn flat round dense color="grey-8" icon="search" /> -->
        <!-- <div class="row justify-center"> -->

        <q-toolbar-title class="q-mt-sm q-mb-sm q-mr-xl text-center">
          <q-input
            v-model="search"
            filled
            type="Search"
            label="Search for a patient"
            class="bg-white"
            :dense="dense"
          >
            <template v-slot:append>
              <q-icon name="search" color="black"></q-icon>
            </template>
          </q-input>
        </q-toolbar-title>

        <!-- </div> -->
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="drawer"
      :mini="!drawer || miniState"
      @click.capture="drawerClick"
      :width="250"
      :breakpoint="500"
      content-class="bg-indigo-6"
    >
    
        <q-item>
          <q-item-section avatar>
            <q-icon
              color="white"
              name="chevron_right"
              v-if="miniState"
              @click.stop="miniState = !miniState"
            ></q-icon>
          </q-item-section>
        </q-item>
        <q-item>
          <q-avatar>
            <img src="https://randomuser.me/api/portraits/men/85.jpg">
          </q-avatar>
          <q-item>
            <q-item-section class="text-white">John Leider</q-item-section>
          </q-item>

          <q-item-section avatar>
            <q-icon color="white" name="chevron_left" @click.stop="miniState = !miniState"></q-icon>
          </q-item-section>
        </q-item>

        <q-item>
          <q-btn v-if="miniState" round color="red-10" icon="add"/>

          <q-btn v-if="!miniState" color="red-10" icon="add" label="ADD PATIENT"/>
        </q-item>

        <q-list v-for="item in items" :key="item.title">
          <q-item clickable v-ripple>
            <q-item-section avatar>
              <q-icon :name="item.icon" color="white"></q-icon>
            </q-item-section>
            <q-tooltip v-if="miniState" anchor="center right" self="center left" :offset="[10, 10]">
              <strong>{{ item.title }}</strong>
            </q-tooltip>
            <q-item-section class="text-grey-1">{{ item.title }}</q-item-section>
          </q-item>
        </q-list>
      
    </q-drawer>
    <q-page-container>
      <router-view/>
    </q-page-container>
  </q-layout>
</template>

<script>
export default {
  name: "MyLayout",
  data() {
    return {
      search: "",
      drawer: true,
      miniState: true,
      dense: true,
      items: [
        { title: "Home", icon: "dashboard" },
        { title: "Patients", icon: "hotel" },
        { title: "Task Manager", icon: "assignment_turned_in" },
        { title: "Alerts", icon: "notifications_active" },
        { title: "Messages", icon: "email" },
        { title: "Population Manager", icon: "bar_chart" },
        { title: "Admin", icon: "person" }
      ]
    };
  },
  methods: {
    drawerClick(e) {
      // if in "mini" state and user
      // click on drawer, we switch it to "normal" mode
      if (this.miniState) {
        this.miniState = false;

        // notice we have registered an event with capture flag;
        // we need to stop further propagation as this click is
        // intended for switching drawer to "normal" mode only
        e.stopPropagation();
      }
    }
  }
};
</script>

<style></style>
