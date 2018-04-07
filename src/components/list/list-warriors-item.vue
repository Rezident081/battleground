<template>
  <li class="list-item">
      <ItemTitle :title="type" :count="total" />
      <ItemBody :image="image" />
  </li>
</template>

<script>

import ItemTitle from "./list-warriors-item-title"
import ItemBody from "./list-warriors-item-body"

export default {
    props: {
        id : {
            type : Number
        },
        type:{
            type : String
        },
        health:{
            type : Number
        },
        distance:{
            type : Number
        },
        damage:{
            type: Number
        },
        image: {
            type: String
        },
        total: {
            type: Number
        }
    },
    components:{
        ItemTitle,
        ItemBody,
    }
}
</script>
