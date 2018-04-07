<template>
    <div class="list-container">
        <p class="title">List of warriors:</p>
        <ul class="warriors-list">
            <ListItem 
                v-for="{id, type, health, distance, damage} of totalSquad" 
                :key="id" 
                :id="id"
                :type="type"
                :health="health"
                :distance="distance"
                :damage="damage"
                :image="setImage(type)"
                :total="totalCount[type]"
                v-tooltip.bottom="`
                    <p>Type : ${type}</p>
                    <p>Health : ${health} </p>
                    <p>Damage : ${damage} </p>
                    <p>Total : ${totalCount[type]} </p>
                `"
            />
        </ul>
    </div>
</template>

<script>

import ListItem from "./list-warriors-item"
import squad from "../../models/my_squad.json"
import archerImg from "../../assets/archer.png"
import knightImg from "../../assets/knight.png"
import cavalryImg from "../../assets/cavalry.png"
import uniqBy from "lodash/uniqBy"
import countBy from "lodash/countBy"

export default {

    components:{
        ListItem
    },

    data(){
        return {
            squad
        }
    },

    computed:{

        totalSquad(){
            return uniqBy(this.squad, "type")
        },

        totalCount(){
            return countBy(this.squad, "type");
        }

    },

    methods:{ 

        setImage(type){
            switch (type) {
                case "archer" : return archerImg;
                case "knight" : return knightImg;
                case "cavalry" : return cavalryImg;
            }
        },


    }

}
</script>
