<template>
    <form-field :field-class="'check-in-field'" :field-target="'qikres-check-in-date'" :label-text="label">
        <input type="date" id="qikres-check-in-date" :value="checkInDate" v-on:input="$emit('input', $event.target.value)" >
    </form-field>
</template>

<script>
    import FormField from "./FormField.vue";

    export default{
        name: "CheckInField",
        components : {
            "form-field" : FormField
        },
        props : {
            checkInDate : String
        },
        data(){
            return {
                label : "Check In"
            }
        }
    }
</script>