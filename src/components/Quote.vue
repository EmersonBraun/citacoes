<template>
    <div class="quotes">
        <slot name="author"></slot>
        <slot name="quote"></slot>
        <slot name="profession"></slot>
        <slot name="topics"></slot>
    </div>
</template>

<script>
export default {
    
}
</script>

<style scoped>
    .quotes {
        border: 1px solid #DDD;
        background-color: rgba(0, 0, 0, .1);
        padding: 25px;
        width: clamp(350px, 600px);
        max-width: 600px;
        height: clamp(200px, 100%);
    }
</style>
