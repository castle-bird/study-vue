<template lang="">
    <nav>
        <a href="#">home</a>
        <a href="#">movies</a>
        <a href="#">about</a>

        {{text}}
    </nav>
</template>

<script>
export default {
    name: "NavbarComponent",
    props: {
        text: String
    }
};
</script>

<style></style>
