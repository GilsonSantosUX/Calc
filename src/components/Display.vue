<template>
    <div class="display">
        {{number}}
        <slot name="icon"></slot>
    </div>
</template>

<script>

export default {
    name:"Display",
    props:{
        number:{
            type:String,
            default:''
        }
    }
}
</script>

<style lang="scss">
    .display{
        font-family:var(--font-secondary);
        font-weight:400;
        width:100%;
        padding:24px;
        text-align:right;
        font-size:3rem;
    }
</style>