<template>
    <button @click="onClick">My button</button>
</template>

<script lang="ts">
    import {Component,Emit,Prop,Vue} from "vue-property-decorator";
    @Component
    export default class MyButton extends Vue{
        private count = 0;
        @Prop()
        public greet?: string;

        @Emit("click")
        public onClick(){
            //alert(this.greet);
            this.count++;
            return this.count;
        }
    }

</script>