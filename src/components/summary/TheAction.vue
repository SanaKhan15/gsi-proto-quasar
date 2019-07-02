<template>
  <div class="q-pa-md">
    <demo-card :heading="heading" class="text-grey" :btnType="'add'">
      <q-card-section class="q-ml-lg q-mb-lg">
        <q-btn-toggle
          v-model="model"
          toggle-color="grey"
          :options="[
            {label: 'Due today', value: 'one'},
            {label: 'Due this week', value: 'two'},
            {label: 'All', value: 'three'}
          ]"
        />
      </q-card-section>

      <q-list v-for="item in items" :key="item.id">
        <q-item>
          <q-item-section avatar class="q-ml-lg">
            <q-btn unelevated round color="green-9">
              <q-icon :name="item.icon" color="white"></q-icon>
            </q-btn>
          </q-item-section>

          <q-item-section class="q-ml-lg">
            <q-item-label class="text-black text-subtitle1">{{ item.text }}</q-item-label>
            <q-item-label>{{item.date}}</q-item-label>
            <q-item-label caption>{{item.title}}</q-item-label>
          </q-item-section>
        </q-item>

        <q-separator inset="item-thumbnail" />
      </q-list>
    </demo-card>
  </div>
</template>

<script>
import DemoCard from "../customCard/DemoCard";
export default {
  name: "Action",
  data() {
    return {
      model: "one",
      heading: "Actions",
      actionItems: [
        {
          id: 0,
          icon: "show_chart",
          iconClass: "green darken-3 white--text",
          title: "Assessment",
          text: "CANS and Monthly Billing",
          date: "02/21/2019"
        },
        {
          id: 1,
          icon: "show_chart",
          iconClass: "green darken-3 white--text",
          title: "Assessment",
          text: "HML Assessment",
          date: "02/21/2019"
        },
        {
          id: 2,
          icon: "assignment",
          iconClass: "blue white--text",
          title: "Encounter",
          text: "Monthly Encounter",
          date: "02/17/2019"
        },
        {
          id: 3,
          icon: "assignment",
          iconClass: "blue white--text",
          title: "Encounter",
          text: "Initial Encounter",
          date: "02/20/2019"
        },
        {
          id: 4,
          icon: "show_chart",
          iconClass: "green darken-3 white--text",
          title: "Assessment",
          text: "Monthly Billing",
          date: "05/21/2019"
        },
        {
          id: 5,
          icon: "show_chart",
          iconClass: "green darken-3 white--text",
          title: "Assessment",
          text: "Initial Encounter",
          date: "02/20/2019"
        }
      ]
    };
  },

  components: {
    DemoCard
  },
  computed: {
    items() {
      if (this.model === "one") {
        return this.actionItems;
      }
      if (this.model === "two") {
        return this.actionItems.filter(alert => alert.title === "Assessment");
      }
      if (this.model === "three") {
        return this.actionItems.filter(alert => alert.title === "Encounter");
      }
      return this.actionItems;
    }
  }
};
</script>