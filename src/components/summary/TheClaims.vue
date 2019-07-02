<template>
  <div class="q-pa-md">
    <demo-card :heading="heading" class="text-grey" :btnType="'add'">
      <q-scroll-area style="height: 480px;">
        <q-list v-for="item in claimItems" :key="item.id">
          <q-banner class="text-grey-10 bg-indigo-1 q-ml-md q-mr-md">
            <span class="text-weight-bold">{{item.text}}</span>
            <q-chip class="float-right" color="grey-14 text-white">{{item.amount}}</q-chip>
            <br />
            <span class="caption">Claim ID:</span>
            {{item.id}}
            <br />
            {{ item.date }}
          </q-banner>
          <br />
        </q-list>
      </q-scroll-area>
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
      heading: "Claims",
      claimItems: [
        {
          id: 345,
          text: "PCP visit",
          date: "12/15/2018",
          amount: "$75"
        },
        {
          id: 567,
          text: "Therapy 60 minutes",
          date: "09/22/2018",
          amount: "$120"
        },
        {
          id: 890,
          text: "Chest X-ray",
          date: "09/20/2018",
          amount: "$225"
        },
        {
          id: 575,
          text: "PCP visit",
          date: "06/15/2018",
          amount: "$95"
        },
        {
          id: 765,
          text: "Leg X-ray",
          date: "06/16/2018",
          amount: "$105"
        },
        {
          id: 575,
          text: "PCP visit",
          date: "06/15/2018",
          amount: "$95"
        },
        {
          id: 765,
          text: "Leg X-ray",
          date: "06/16/2018",
          amount: "$105"
        }
      ]
    };
  },

  components: {
    DemoCard
  }
};
</script>