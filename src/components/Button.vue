<template>
    <button>
        {{number}}
        <slot name="icon" class="icon"></slot>
    </button>
</template>

<script>
export default {
    name:"Button",
    props:{
        number:{
            type:String,
            defualt:''
        }
    }
}
</script>

<style lang="scss">
    button{
        border:none;
        background: transparent;
        display:flex;
        justify-content:center;
        align-items:center;
        padding:8px 24px;
        height:96px;
        min-width:120px;
        font-family:var(--font-secondary);
        font-weight:500;
        font-size:3rem;
        border-radius:16px;
        color:var(--color-base-white);
        cursor:pointer;
        user-select: none;
        &:focus{
            outline: transparent auto 0px;
        }
        &:hover{
            background:var(--theme-color-base);
            &.active{
                background: #A62B2B;
            }
        }
        &.active{
            background: #C53D3D;
        }
        path{
            fill:var(--color-base-white);
        }
    }
</style>