<template>
    <div class="modal-container">
        <button @click="isOpen = true">{{ openLabel }}</button>

        <teleport to="#app">
            <div class="modal" v-show="isOpen">
                <div class="modal-content">
                    <slot />

                    <button class="close" @click="isOpen = false">
                        {{ closeLabel }}
                    </button>
                </div>
            </div>
        </teleport>
    </div>
</template>

<script setup>
import { ref, defineProps } from 'vue';

const isOpen = ref(false);

defineProps({
    openLabel: String,
    closeLabel: String,
});
</script>

<style scoped>
.modal {
    z-index: 100;
    position: absolute;
    inset: 0;
    background: rgba(0, 0, 0, 0.2);
    display: flex;
    justify-content: center;
    align-items: center;
}

.modal-content {
    position: relative;
    background: #fff;
    padding: 20px;
    border-radius: 10px;
}

.close {
    position: absolute;
    right: 10px;
    top: 10px;
}
</style>
