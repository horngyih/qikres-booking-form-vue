<template>
    <form-field :field-class="'adultcount-field'" :field-target="'qikres-adultcount'" :label-text="label">
        <number-field :field-id="'qikres-adultcount'" :max="9" :min="1"></number-field>
    </form-field>
</template>

<script>
    import FormField from "./FormField";
    import NumberField from "./NumberField.vue";
    export default {
        name : "AdultCount",
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