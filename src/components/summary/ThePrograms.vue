<template>
  <div class="q-pa-md">
    <!-- <iconcard :heading="heading">  -->
    <app-demo-card :heading="heading" class="text-grey" :btnType="'list'">
      <q-card-section class="q-ml-lg q-mb-lg">
        <q-btn-toggle
          v-model="model"
          toggle-color="grey"
          :options="[
            {label: 'ACTIVE', value: 'one'},
            {label: 'PENDING', value: 'two'}
           
          ]"
        />
      </q-card-section>

      <q-list v-for="item in items" :key="item.id">
        <q-item>
          <!-- <q-item-section>{{ items.text }}</q-item-section> -->

          <q-item-section class="q-ml-lg">
            <q-item-label class="text-black text-subtitle1">{{ item.text }}</q-item-label>
            <q-item-label>{{item.date}}</q-item-label>
          </q-item-section>
        </q-item>
        <q-separator class="seperator-margin" inset/>
      </q-list>
    </app-demo-card>
    <!-- </iconcard> -->
  </div>
</template>
<script>
import DemoCard from "../customCard/DemoCard";
export default {
  name: "Action",
  data() {
    return {
      model: "one",
      heading: "Programs",
      programItems: [
        {
          id: 0,
          title: "Active",
          text: "City Cares",
          date: "11/12/2018"
        },
        {
          id: 1,
          title: "Active",
          text: "Town Health Home",
          date: "10/13/2018"
        },
        {
          id: 2,
          title: "Pending",
          text: "Town Health Home",
          date: "17/11/2018"
        },
        {
          id: 3,
          title: "Active",
          text: "City Cares",
          date: "11/18/2019"
        },
        {
          id: 4,
          title: "Active",
          text: "Town Health Home",
          date: "17/11/2018"
        },
        {
          id: 5,
          title: "Active",
          text: "City Cares",
          date: "11/18/2019"
        },
        {
          id: 6,
          title: "Active",
          text: "Town Health Home",
          date: "17/11/2018"
        }
      ]
    };
  },

  components: {
    appDemoCard: DemoCard
  },
  computed: {
    items() {
      if (this.model === "one") {
        return this.programItems;
      }
      if (this.model === "two") {
        return this.programItems.filter(alert => alert.title === "Active");
      }
      return this.programItems;
    }
  }
};
</script>
<style scoped>
.seperator-margin{
  margin-left: 33px;
}
</style>
