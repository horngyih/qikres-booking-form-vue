<template>
    <form-field :field-class="fieldClass" :field-target="fieldID" :label-text="label">
        <select :id="fieldID" :name="fieldID" :value="propertyCode" v-on:change="$emit( 'input', $event.target.value)">
            <option value="">-- Select Property</option>
            <option v-for="property in properties" :key="property.code" :value="property.code">{{property.name}}</option>
        </select>
    </form-field>
</template>

<script>
    import FormField from "./FormField.vue";

    export default{
        name : "PropertyField",
        components : {
            "form-field" : FormField
        },
        props : {
            propertyCode : String
        },
        data(){
            return {
                label : "Properties",
                fieldClass  : "property-field",
                fieldID : "qikres-property-field",
                properties : [
                    {
                        name : "Qikinn Hotel",
                        code : "QIK"
                    },
                    {
                        name : "Qiknn Resort",
                        code : "QIR"
                    }
                ]
            };
        }
    }
</script>