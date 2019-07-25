<template>
    <div class="clearAllContainer">
        <button class="clearAllBtn" @click="clearTodo">Clear All</button>
    </div>
</template>

<script>
    export default {
        methods: {
            clearTodo() {
               this.$emit('removeAll');
            }
        }
    }
</script>

<style scoped>
    .clearAllContainer {text-align:center;}
    .clearAllBtn {width:8.5rem; height:50px; color:#e20303; line-height:50px; background:#fff; border:0; cursor:pointer;}
</style>
