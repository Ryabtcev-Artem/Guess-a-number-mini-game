<template>
    <div v-show="showInput" class="GameBar">
        <!-- Эмитим событие `update:numValue` при изменении значения инпута -->
        <input type="number" :value="modelValue" @input="$emit('update:modelValue', $event.target.value)" placeholder="Введите число">
    </div>
</template>

<script>
export default {
    props: { 
        showInput: {
            type: Boolean,
            required: true,
        },
        modelValue: {
            type: Number,
            required: true,
        }
    },
}
</script>

<style>
    .GameBar {
        width: 100%;
        height: 300px;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: end;
    }
    input {
        text-align: center;
        border-radius: 16px;
        border: 2px solid #000;
        height: 100px;
        width: 30%;
        outline: none;
        font-size: 3.9em;
    }
</style>
