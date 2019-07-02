<template>
  <div class="q-pa-md">
    <demo-card :heading="heading" class="text-grey" :btnType="'add'">
      <q-card-section class="q-ml-lg q-mb-lg">
        <q-btn-toggle
          v-model="model"
          toggle-color="grey"
          :options="[
            {label: 'All', value: 'one'},
            {label: 'Critical', value: 'two'},
            {label: 'High', value: 'three'}
          ]"
        />
      </q-card-section>

      <q-list v-for="item in items" :key="item.id">
        <q-item>
          <q-item-section avatar>
            <q-avatar class="q-ml-lg" :class="[item.iconClass]">
              <q-icon :name="item.icon"></q-icon>
            </q-avatar>
          </q-item-section>

          <q-item-section class="q-ml-lg">
            <q-item-label class="text-black text-subtitle1">{{ item.text }}</q-item-label>
            <q-item-label>{{item.date}}</q-item-label>
            <q-item-label caption>{{item.title}}</q-item-label>
          </q-item-section>
        </q-item>
        <q-separator inset="item-thumbnail" />
      </q-list>

      <view-all-bar :count="alertItems.length" :total="25"></view-all-bar>
    </demo-card>
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
      heading: "Alerts",
      alertItems: [
        {
          id: 0,
          icon: "block",
          iconClass: "bg-red-8 text-white",
          title: "Critical",
          text: "Admitted to ED at Adventist Medical Center",
          date: "11/16/2018",
          time: "1:45 AM"
        },
        {
          id: 1,
          icon: "priority_high",
          iconClass: "bg-orange-7 text-white",
          title: "High",
          text: "Dr. Sarah Test added to care team",
          date: "11/12/2018",
          time: "2:55 PM"
        },
        {
          id: 2,
          icon: "priority_high",
          iconClass: "bg-orange-7 text-white",
          title: "Critical",
          text: "Dr. Taran Test added to care team",
          date: "16/12/2018",
          time: "4:55 PM"
        },
        {
          id: 3,
          icon: "block",
          iconClass: "bg-red-8 text-white",
          title: "Critical",
          text: "Admitted to ED at Adventist Medical Center",
          date: "11/16/2018",
          time: "1:45 AM"
        },
        {
          id: 4,
          icon: "priority_high",
          iconClass: "bg-orange-7 text-white",
          title: "Critical",
          text: "Dr. Taran Test added to care team",
          date: "16/12/2018",
          time: "4:55 PM"
        },
        {
          id: 5,
          icon: "block",
          iconClass: "bg-red-8 text-white",
          title: "Critical",
          text: "Admitted to ED at Adventist Medical Center",
          date: "11/16/2018",
          time: "1:45 AM"
        }
      ]
    };
  },
  components: {
    DemoCard,
    ViewAllBar
  },
  computed: {
    items() {
      if (this.model === "one") {
        return this.alertItems;
      }
      if (this.model === "two") {
        return this.alertItems.filter(alert => alert.title === "Critical");
      }
      if (this.model === "three") {
        return this.alertItems.filter(alert => alert.title === "High");
      }
      return this.alertItems;
    }
  }
};
</script>