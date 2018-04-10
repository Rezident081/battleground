<template>
    <div class="battlefield-container">
        <p class="title">battlefield</p>
        <table class="battlefield-table">
            <tr v-for="row in 4" :key="row">
                <TableItem 
                        v-for="col in 6" 
                        :key="col" 
                />
            </tr>
        </table>
    </div>
</template>

<script>
import TableItem from "./battlefield-table-item"
import squads from "../../models/squads.json"
export default {
    components:{
        TableItem
    },
    data(){
        return {
            squads
        }
    }


}
</script>

