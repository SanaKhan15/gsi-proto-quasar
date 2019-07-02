<template>
  <div>
    <div class="bg-grey-3 row">
      <div class="col">
        <patientGlance></patientGlance>
      </div>
    </div>
    <q-card></q-card>
    <div class="row">
      <div class="col-xs-12 col-md-4 col-lg-4">
        <action></action>
      </div>
      <div class="col-xs-12 col-md-4 col-lg-4">
        <CareTeam></CareTeam>
      </div>
      <div class="col-xs-12 col-md-4 col-lg-4">
        <Alerts></Alerts>
      </div>
    </div>
    <div class="row">
      <div class="col-xs-12 col-md-4 col-lg-4">
        <TheClaims></TheClaims>
      </div>
      <div class="col-xs-12 col-md-4 col-lg-4">
        <ThePrograms></ThePrograms>
      </div>
      <div class="col-xs-12 col-md-4 col-lg-4">
        <TheGaps></TheGaps>
      </div>
    </div>
  </div>
</template>

<script>
import patientGlance from "../components/patientGlance.vue";
import Action from "../components/summary/TheAction.vue";
import CareTeam from "../components/summary/CareTeam";
import Alerts from "../components/summary/TheAlerts";
import ThePrograms from "../components/summary/ThePrograms";
import TheGaps from "../components/summary/TheGaps";
import TheClaims from "../components/summary/TheClaims";
export default {
  data() {
    return {
      tab: "one"
    };
  },
  components: {
    patientGlance,
    Action,
    CareTeam,
    Alerts,
    ThePrograms,
    TheGaps,
    TheClaims
  }
};
</script>

<style>
.container {
  display: flex;
}
</style>




