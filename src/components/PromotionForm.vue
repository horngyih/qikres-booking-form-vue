<template>
    <form-field :field-class="fieldClass" :field-target="fieldID" :label-text="label">
        <input :id="fieldID" type="text">
        <button class="button" type="button">{{actionLabel}}</button>
    </form-field>
</template>

<script>
    import FormField from "./FormField.vue";

    export default{
        name : "PromotionForm",
        components : {
            "form-field" : FormField
        },
        props : {},
        data(){
            return {
                label : "Promotion Code",
                fieldID : "qikres-promotion-code-field",
                fieldClass : "promotion-code-field",
                actionLabel : "Apply Code"
            };
        }
    };
</script>