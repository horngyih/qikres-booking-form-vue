<template>
    <label :for="targetField">
        <span class="label-text">{{labelText}}</span>
        <slot></slot>
    </label>
</template>

<script>
    export default {
        name : "LabelField",
        props : {
            targetField : String,
            labelText: String
        }
    }
</script>