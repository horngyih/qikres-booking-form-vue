<template>
    <form-field :field-class="'qikres-check-out-field'" :field-target="'qikres-check-out-field'" :label-text="label">
        <input type="date" id="qikres-check-out-field">
    </form-field>
</template>

<script>
    import FormField from "./FormField.vue";

    export default{
        name : "CheckOutField",
        components : {
            "form-field" : FormField
        },
        props : {},
        data(){
            return {
                label : "Check Out"
            }
        }
    }
</script>