<template>
    <div class="list-container">
        <p class="title">List of warriors:</p>
        <ul class="warriors-list">
            <ListItem 
                v-for="{id, type, health, distance, damage} of totalSquad" 
                :key="id" 
                :type="type"
                :health="health"
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
import squads from "../../models/squads.json"
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
            squads
        }
    },

    computed:{

        totalSquad(){
            const squad = this.getMySquad(this.squads);
            return uniqBy(squad, "type")
        },

        totalCount(){
            const squad = this.getMySquad(this.squads);
            return countBy(squad, "type");
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

        getMySquad(squads){
            let mySquad = [];
            for (const key in squads) {
                if (squads.hasOwnProperty(key) && squads[key].squad === 1) {
                    mySquad[key] = squads[key];
                }
            }
            return mySquad;
        }


    }

}
</script>
