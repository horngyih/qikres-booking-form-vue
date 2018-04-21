<template>
    <select :name="fieldId" :id="fieldId">
        <option v-for="count in numbers" :key="count" :value="count">{{count}}</option>
    </select>
</template>

<script>
    export default{
        name: "NumberField",
        props : {
            fieldId : String,
            max : Number,
            min : Number
        },
        computed : {
            numbers(){
                let maximum = this.max || 1;
                let minimum = this.min || 1;
                let numbers = [];
                for( let i = minimum; i <= maximum; i++ ){
                    numbers.push( i );
                }
                return numbers;
            }
        }
    }
</script>