<template>
    <form-field :field-class="'qikres-check-out-field'" :field-target="'qikres-check-out-field'" :label-text="label">
        <input type="date" id="qikres-check-out-field" :value="checkOutDate" v-on:input="$emit('input', $event.target.value )">
    </form-field>
</template>

<script>
    import FormField from "./FormField.vue";

    export default{
        name : "CheckOutField",
        components : {
            "form-field" : FormField
        },
        props : {
            checkOutDate : String
        },
        data(){
            return {
                label : "Check Out"
            }
        }
    }
</script>