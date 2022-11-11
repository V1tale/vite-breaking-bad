<script>
import AppCards from "../components/AppCards.vue"
export default {
    name: "AppContainer",
    components: {
        AppCards,
    },
    data() {
        return{

        }
    }
}
</script>

<template>
    <div class="title">
        <img src="../../public/logo.png" alt="Breaking Bad logo">
        <h1>Breaking Bad API</h1>        
    </div>
    <div class="container">
        <div class="wrapper">
            <AppCards />
        </div>
    </div>
</template>

<style lang="scss">

img {
    width: 100px;
}
.title {
    display: flex;
    align-items: center;
    background-color: gray;
    padding-left: 1rem;
    h1 {
        margin-left: 1rem;
        color:white;
    }
}
.wrapper {
    width:100%;
    background-color:white;
}
</style>