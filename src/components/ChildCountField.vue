<template>
    <form-field :field-class="fieldClass" :field-target="fieldID" :label-text="label">
        <number-field :field-id="id" :max="maxCount" :min="minCount"></number-field>
    </form-field>
</template>

<script>
    import FormField from "./FormField.vue";
    import NumberField from "./NumberField.vue";
    export default {
        name : "ChildCountField",
        components : {
            "form-field" : FormField,
            "number-field" : NumberField
        },
        props : {

        },
        data() {
            return {
                label : "Children",
                fieldClass : "childcount-field",
                fieldID : "qikres-childcount-field",
                maxCount : 5,
                minCount : 0
            }
        }
    };
</script>