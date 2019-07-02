<template>
  <div class="q-pa-md">
    <demo-card :heading="heading" class="text-grey" :btnType="'list'">
      <q-list v-for="item in items" :key="item.id">
        <q-item>
          <q-item-section class="q-ml-lg q-mt-md">
            <q-item-label class="text-grey-7 text-subtitle1">{{ item.text }}</q-item-label>
          </q-item-section>
        </q-item>
        <q-separator class="seperator-margin" inset />
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
      heading: "Gaps in Care",
      items: [
        { id: 0, text: "Mammogram" },
        { id: 1, text: "Foot exam" },
        { id: 2, text: "Eye exam" },
        { id: 3, text: "Brain exam" },
        { id: 4, text: "Skin exam" },
        { id: 5, text: "Mammogram" }
      ]
    };
  },

  components: {
    DemoCard
  }
};
</script>

<style scoped>
.seperator-margin {
  margin-left: 33px;
}
</style>
