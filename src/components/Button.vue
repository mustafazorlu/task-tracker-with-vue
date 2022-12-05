<template>
    <button v-on:click="onClick()" class="btn" v-bind:style="{background:color}">
        {{buttonText}}
    </button>
    
</template>

<script>
    export default {
        name : 'Button',
        props:{
            buttonText:String,
            color:String
        },
        methods:{
            onClick(){
                this.$emit('btn-click')
            },
        }
    }
</script>