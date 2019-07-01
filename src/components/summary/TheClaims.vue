<template>
  <div class="q-pa-md">
    <!-- <iconcard :heading="heading">  -->
    <app-demo-card :heading="heading" class="text-grey" :btnType="'add'">
      <!-- <banner-light v-for="item in claimItems" :key="item.id"> -->

      <q-list v-for="item in claimItems" :key="item.id">
        <q-banner class="text-grey-10 bg-indigo-1 q-ml-md q-mr-md">
          <span class="text-weight-bold">{{item.text}}</span>
          <q-chip class="float-right" color="grey-14 text-white">{{item.amount}}</q-chip>
          <br>
          <span class="caption">Claim ID:</span>
          {{item.id}}
          <br>
          {{ item.date }}
        </q-banner>
        <br>
      </q-list>

      <!-- </banner-light> -->
    </app-demo-card>
    <!-- </iconcard> -->
  </div>
</template>
<script>
import DemoCard from "../customCard/DemoCard";
// import BannerLight from "../customCard/BannerLight"
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
        }
        //   {
        //   id: 795,
        //   text: "Leg X-ray",
        //   date: "06/16/2018",
        //   amount: "$105"
        // }
      ]
    };
  },

  components: {
    appDemoCard: DemoCard
    // BannerLight
  }
};
</script>