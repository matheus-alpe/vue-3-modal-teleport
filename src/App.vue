<script setup>
import Modal from './components/Modal.vue';
</script>

<template>
    <Modal open-label="Open Modal" close-label="x">
        <h2>Success</h2>
        <p>A success message.</p>
    </Modal>

    <!-- this works because v-show on .modal -->
    <teleport to=".modal-content">
        <h2>Error</h2>
        <p>A error message.</p>
    </teleport>
</template>

<style>
body {
    min-height: 100vh;
    margin: 0;
    padding: 0;
}

#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>
