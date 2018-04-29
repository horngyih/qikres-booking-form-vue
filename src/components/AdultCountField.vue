<template>
    <form-field :field-class="'adultcount-field'" :field-target="'qikres-adultcount'" :label-text="label">
        <number-field :value="value" :field-id="'qikres-adultcount'" :max="9" :min="1" v-on:input="$emit('input', parseInt($event))"></number-field>
    </form-field>
</template>

<script>
    import FormField from "./FormField";
    import NumberField from "./NumberField.vue";
    export default {
        name : "AdultCount",
        props : {
            value : Number
        },
        components: {
            "form-field" : FormField,
            "number-field" : NumberField
        },
        data(){
            return {
                label : "Adults",
                maxCount : 9
            };
        }
    }
</script>