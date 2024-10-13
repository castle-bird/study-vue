<script setup>
import { ref } from 'vue';
import Header from "./components/Header.vue";
import Update from "./components/Update.vue";
import List from "./components/List.vue";

// mocData를 ref로 관리하여 반응형 상태로 설정
const mocData = ref([
    { id: 0, isDone: false, workList: "뷰 공부하기" },
    { id: 1, isDone: false, workList: "뷰 공부하기2" },
    { id: 2, isDone: false, workList: "뷰 공부하기3" },
]);

const onUpdate = (data) => {
    // 새로운 작업을 추가한 후, 기존 배열에 추가
    const newItem = {
        id: mocData.value.length,
        isDone: false,
        workList: data,
    };
    mocData.value.push(newItem);
    console.log('Updated mocData:', mocData.value);
};
</script>

<template>
    <div class="wrap">
        <Header />
        <Update :onUpdate="onUpdate" />
        <List :mocData="mocData" />
    </div>
</template>

<style scoped></style>
