<template>
  <div id="app">
    <h1>{{headerText}}</h1>
    <property-field :property-code="bookingForm.propertyCode" v-on:input="bookingForm.propertyCode=$event"></property-field>
    <check-in-field :check-in-date="bookingForm.checkInDate.toString()" v-on:input="bookingForm.checkInDate=$event"></check-in-field>
    <nights-field :nights="nights" v-on:input="setNights($event)"></nights-field>
    <check-out-field :check-out-date="bookingForm.checkOutDate.toString()" v-on:input="bookingForm.checkOutDate=$event"></check-out-field>
    <adult-count-field v-model="bookingForm.adultCount"></adult-count-field>
    <child-count-field :child-count="bookingForm.childCount" v-on:input="bookingForm.childCount=parseInt($event)"></child-count-field>
    <promotion-form></promotion-form>
    <button class="button primary">{{actionLabel}}</button>

    <div class="bookingForm">
      <form action="#">
        <legend>Booking Form</legend>
        <fieldset>
          <div>
            <p><b>Property Code</b> : {{bookingForm.propertyCode}}</p>
          </div>
          <div>
            <p><b>Check In Date </b> : {{bookingForm.checkInDate}}</p>
          </div>
          <div>
            <p><b>Check Out Date</b> : {{bookingForm.checkOutDate}}</p>
          </div>
          <div>
            <p><b>Adults Count</b> :  {{bookingForm.adultCount}}</p>
          </div>
          <div>
            <p><b>Child Count</b> :  {{bookingForm.childCount}}</p>
          </div>
        </fieldset>
      </form>
    </div>
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
      actionLabel : "Book Now",
      bookingForm : {
        propertyCode : "QIK",
        checkInDate : new Date(),
        checkOutDate : new Date(),
        adultCount : 2,
        childCount : 0
      }
    };
  },
  computed :{
    nights(){
      return 1;
    }
  },
  methods:{
    setNights( nights ){
      let startDate = new Date( this.bookingForm.checkInDate );
      let startDateTime = startDate.getTime();
      let endDateTime = startDateTime + ( parseInt( nights ) * 1000 * 60 * 60 * 24 );
      let endDate = new Date( endDateTime );
      this.bookingForm.checkOutDate = endDate;
    }
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
