<template>
  <div id="app">
    <h1>{{headerText}}</h1>
    <property-field></property-field>
    <check-in-field></check-in-field>
    <nights-field></nights-field>
    <check-out-field></check-out-field>
    <adult-count-field></adult-count-field>
    <child-count-field></child-count-field>
    <promotion-form></promotion-form>
    <button class="button primary">{{actionLabel}}</button>
  </div>
</template>

<script>

import PropertyField from "./components/PropertyField.vue";
import CheckInField from './components/CheckInField.vue';
import NightsField from "./components/NightsField.vue";
import CheckOutField from './components/CheckOutField.vue';
import AdultCountField from "./components/AdultCountField.vue";
import ChildCountField from "./components/ChildCountField.vue";

import PromotionForm from "./components/PromotionForm.vue";

export default {
  name: 'qikresBookingForm',
  components: {
    PropertyField,
    CheckInField,
    NightsField,
    CheckOutField,
    AdultCountField,
    ChildCountField,
    PromotionForm
  },
  data(){
    return {
      headerText : "Booking Form",
      actionLabel : "Book Now"
    };
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
