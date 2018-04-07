<template>
    <div class="list-item__title">{{title}} <sup>{{count}}</sup> </div>
</template>

<script>
export default {
    props:{
        title :{
            type: String
        },
        count :{
            type: Number
        }
    }
}
</script>

