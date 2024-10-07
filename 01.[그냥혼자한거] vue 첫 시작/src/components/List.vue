<script setup>
    const props = defineProps({
        mocData: {
            type: Array,
            required: true
        }
    });
</script>

<template>
    <div class="list-area">
        <table border="1" width="100%" style="margin-top: 20px;">
            <thead>
                <th>번호</th>
                <th>체크</th>
                <th>내용</th>
                <th>삭제</th>
            </thead>
            <tbody>
                <tr v-for="data in mocData" align="center">
                    <td>
                        <span>{{ data.id + 1 }}</span>
                    </td>

                    <td>
                        <input
                            type="checkbox"
                            name=""
                            id=""
                            :value="data.isDone"
                        />
                    </td>
                    <td>
                        <p>{{ data.workList }}</p>
                    </td>
                    <td><button>삭제</button></td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<style scoped></style>
