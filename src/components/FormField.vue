<template>
    <div class="form-field" :class="fieldClass">
        <label-field :target-field="targetField" :label-text="labelText">
            <slot></slot>
        </label-field>
    </div>
</template>

<script>
    import LabelField from "./LabelField.vue";

    export default{
        name: "FormField",
        components : {
            "label-field" : LabelField
        },
        props: {
            "fieldClass" : String,
            "targetField" : String,
            "labelText" : String
        }
    }
</script>