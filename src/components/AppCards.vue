<script>
import axios from "axios" 
import {reactive} from "vue";
export default {
    name: "AppCards",
    data() {
        return {
            characters:[],
        }
    },
    created() {
        axios.get("https://www.breakingbadapi.com/api/characters").then((resp) => {
            this.characters = resp.data
            console.log(this.characters);
            this.characters.push(characters);
        } )
    },
}
</script>

<template>
    <div class="cards flex">
        <h1>{{characters}}</h1>
    </div>
</template>

<style lang="scss">

</style>