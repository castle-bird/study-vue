<template>
    <Navbar text="asdasdasd"/>

    <h1>영화정보</h1>
    <div v-for="({ title, year, category, like, imgUrl }, idx) in data" key="idx">
        <figure>
            <img :src="`${imgUrl}`" :alt="title" />
        </figure>
        <h3>{{ title }}</h3>
        <p>개봉 {{ year }}</p>
        <p>장르: {{ category }}</p>
        <button @:click="increseLike(idx)">조아요</button>
        <span>{{ like }}</span>
        <p><button @:click="isModal = true; seletedMovie=idx; ">상세정보</button></p>
    </div>

    <div class="modal" v-if="isModal">
        <div class="inner">
            <h3>{{data[seletedMovie].title}}</h3>
            <p>{{data[seletedMovie].category}}</p>
            <button @:click="isModal = false">닫기</button>
        </div>
    </div>
</template>

<script>
import data from "./assets/movies";
import Navbar from "./components/Navbar.vue";

export default {
    name: "App",
    data() {
        return {
            isModal: false,
            data: data,
            seletedMovie: 0,
        };
    },
    methods: {
        increseLike(idx) {
            this.data[idx].like += 1;
        },
    },
    components: {
        Navbar: Navbar
    }
};
</script>

<style>
.bg {
    background-color: #999999;
}

button {
    cursor: pointer;
}
img {
    width: 300px;
}

.modal {
    position: fixed;
    inset: 0 0 0 0;
    background-color: rgba(0 0 0 / 25%);

    .inner {
        position: absolute;
        left: 50%;
        top: 50%;

        width: 300px;
        height: 300px;

        transform: translate(-50%, -50%);
        background-color: #fff;
    }
}
</style>
