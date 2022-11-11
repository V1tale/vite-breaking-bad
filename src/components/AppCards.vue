<script>
import axios from "axios" 
import {reactive} from "vue";
export default {
    name: "AppCards",
    data() {
        return {
            characters:[],
            category: ["Breaking bad", "Better Call Saul"],
        }
    },
    created() {
        axios.get("https://www.breakingbadapi.com/api/characters").then((resp) => {
            this.characters = resp.data
            console.log(this.characters);
        } )
    },
}
</script>

<template>
    <select name="categories" id="categories">
    <option value="">Select Category</option>
    <option v-for="(series, index) in category" @change="filter()" value="Option">{{series}}</option>
</select>
    <div class="found">
        <h2>Trovati {{characters.length}} personaggi</h2>
    </div>
    <div class="cards">
        <div class="card" v-for="(card, index) in characters" key="index" >
            <img :src="characters[index].img" alt="">
            <h2>{{characters[index].name}}</h2>
            <h3>{{characters[index].portrayed}}</h3>
            <h3>{{characters[index].category}}</h3>
            <h3>{{characters[index].status}}</h3>
        </div>
    </div>
</template>

<style lang="scss">
    .cards {
        display:flex;
        flex-wrap: wrap;
        justify-content: center;
        .card {
            width: calc(100% / 5);
            background-color: #2e3a46;
            padding: .5rem;
            margin:.5rem;
            text-align: center;
            img {
                width:100%;
            }
            h2 {
                color:white;
                font-size: 1.2rem;
            }
            h3 {
                color:gray;
                font-size: .8rem;
            }
        }

    }
    .found {
        padding:.2rem .5rem;;
        color:white;
        background-color:#1b2229 ;
    }
</style>