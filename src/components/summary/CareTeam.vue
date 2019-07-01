<template>
  <div class="q-pa-md">
    <!-- <iconcard :heading="heading">  -->
    <app-demo-card :heading="heading" class="text-grey" :btnType="'list'">
      <p class="q-ml-lg">
        Care team assigned:
        <span class="text-h6 text-black">Care Team 1</span>
      </p>

      <q-list v-for="item in careItems" :key="item.id">
        <q-item>
          <q-item-section avatar class="q-ml-lg">
            <!-- <q-btn unelevated round color="green-9"> -->
            <q-avatar class="primary mr-2 mb-2" color="grey" text-color="black">{{item.initial}}</q-avatar>
            <!-- </q-btn> -->
          </q-item-section>

          <!-- <q-item-section>{{ items.text }}</q-item-section> -->

          <q-item-section class="q-ml-lg q-mt-md">
            <q-item-label class="text-black text-subtitle1">{{ item.text }}</q-item-label>
            <q-item-label class="q-mt-lg">{{item.title}}</q-item-label>
          </q-item-section>
        </q-item>
        <q-separator inset="item-thumbnail"/>
      </q-list>
      <view-all-bar :count="careItems.length" :total="8"></view-all-bar>
    </app-demo-card>
    <!-- </iconcard> -->
  </div>
</template>
<script>
import DemoCard from "../customCard/DemoCard";
import ViewAllBar from "../shared/ViewAllBar";
export default {
  name: "Action",
  data() {
    return {
      model: "one",
      heading: "Care Team",
      careItems: [
        {
          id: 0,
          title: "Care Manager",
          initial: "MS",
          text: "Melanie Smith, ADMIN"
        },
        {
          id: 1,
          title: "ED Patient Navigator",
          initial: "SP",
          text: "Sharon Pown, SOCIAL"
        },
        {
          id: 2,
          title: "Manager",
          initial: "S",
          text: "Smith, ADMIN"
        },
        {
          id: 3,
          title: "Patient Navigator",
          initial: "MS",
          text: "Melanie Smith, SOCIAL"
        },
        {
          id: 4,
          title: "Manager",
          initial: "S",
          text: "Smith, ADMIN"
        },
        {
          id: 5,
          title: "Manager",
          initial: "MS",
          text: "Melanie Smith, SOCIAL"
        }
      ]
    };
  },

  components: {
    appDemoCard: DemoCard,
    ViewAllBar
  }
};
</script>