<template>
    <div class="modal-wrapper">
        <div class="modal-content">
            <slot/>
        </div>
    </div>

</template>

<script>

export default {
       name: 'MyModal',
    }
</script>
<style scoped>
.modal-wrapper {
    position: absolute;
    display: flex;
    align-items: center;
    justify-content: center;
    top: 0;
    left: 0;
    width: 0;
    height: 0;
    background: rgba(0,0,0, .90);
}
</style>
