<template>
    <button @click="onClick">Reset Button</button>
</template>

<script lang="ts">
    import {Component,Emit,Prop,Vue} from "vue-property-decorator";

    @Component
    export default class ResetButton extends Vue {
        @Prop()
        public initialValue!: string;
        
        @Prop()
        public value!: string;

        @Emit("input")
        
        public onClick(value: string){
            return this.initialValue;
        }

    }
</script>