<script setup>
import { ref } from 'vue';

const props = defineProps({
    onUpdate: {
        type: Function,
        required: true,
    },
});

// input 값을 관리할 상태
const inputValue = ref('');

const addWork = () => {
    if (inputValue.value.trim()) {
        props.onUpdate(inputValue.value);
        inputValue.value = '';
        inputValue.text = '';
    }
};
</script>

<template>
    <div class="search-area">
        <input type="text" v-model="inputValue" placeholder="할 일을 입력하세요" />
        <button @click="addWork">추가</button>
    </div>
</template>

<style scoped></style>
