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
            <select name="categories" id="categories">
                <option value="">Select Category</option>
            </select>
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
    h1 {
        margin-left: 1rem;
        color:white;
    }
}
.wrapper {
    width:100%;
    height: 500px;
    background-color:white;
}
</style>