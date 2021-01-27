<template>
<div>
 <button @click="onClick" class="btn">
        <slot> BTN </slot>
    </button>
</div>
   
</template>

<script>
export default {
    name: "Button",
    props: {
        onClick: {
            type: Function,
            required: true
        }
    }
}
</script>

<style scoped>
    button{
        margin: 0 1em 0 0;
        width: 10em;
        display: flex;
        flex: column;
        justify-content: center;
        align-items: center;
        
    }

</style>