<template>
    <form-field :field-class="fieldClass" :field-target="fieldID" :label-text="label">
        <number-field :value="nights" :field-id="fieldID" :max="maxCount" :min="minCount" v-on:input="$emit('input', $event)"></number-field>
    </form-field>
</template>

<script>
    import FormField from "./FormField.vue";
    import NumberField from "./NumberField.vue";

    export default {
        name : "NightsField",
        components : {
            "form-field" : FormField,
            "number-field" : NumberField
        },
        props : {
            nights : Number
        },
        data(){
            return {
                label : "Nights",
                fieldClass : "nights-field",
                fieldID : "qikres-nights-field",
                maxCount : 99,
                minCount : 1                
            }
        }
    };
</script>