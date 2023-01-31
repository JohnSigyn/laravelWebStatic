<script setup>
import { onMounted, ref } from 'vue';

defineProps(['modelValue','minimum','maximum','maxLength']);

defineEmits(['update:modelValue']);

const input = ref(null);

onMounted(() => {
    if (input.value.hasAttribute('autofocus')) {
        input.value.focus();
    }
});
</script>

<template>
    <input class=" outline-gray-300 focus:outline-2 focus:ring-0 border-none outline outline-2 focus:outline-outlineBlue  rounded-md shadow-sm 2xl:py-2 xl:py-1 2xl:text-md xl disabled:bg-gray-100" :value="modelValue" :maxLength="maxLength?maxLength:'50'" :min="minimum?minimum:0" :max=maximum @input="$emit('update:modelValue', $event.target.value)" ref="input">
</template>
