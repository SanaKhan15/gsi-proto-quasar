<template>
  <q-card class="my-card q-ml-md">
    <q-item class="q-ml-md">
      <q-item-section>
        <h6>{{heading}}</h6>
      </q-item-section>

      <q-item-section align="right">
        <q-btn v-if="btnType === 'add'" round outline color="indigo">
          <q-icon name="add" color="black"></q-icon>
        </q-btn>
      </q-item-section>
      <q-item>
        <q-item-section align="right">
          <q-btn v-if="btnType === 'list'" round outline color="indigo">
            <q-icon name="add" color="black"></q-icon>
          </q-btn>
        </q-item-section>
        <q-item-section align="right">
          <q-btn v-if="btnType === 'list'" round outline color="indigo" class="q-ml-sm">
            <q-icon name="list" color="black"></q-icon>
          </q-btn>
        </q-item-section>
      </q-item>
    </q-item>

    <slot></slot>
  </q-card>
</template>
<script>
export default {
  name: "demo",
  props: {
    heading: String,
    btnType: String
  }
};
</script>
 <style scoped>
.my-card {
  border-radius: 20px;
   /* width: 550px; */
  height: 750px  ;
  /* height:100%; */
 /* width: 100%; */ 
}
</style>




