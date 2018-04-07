<template>
  <div class="list-item__body">
      <img :src="image" alt="Unit logo">
  </div>
</template>

<script>
export default {
    props:{
        image:{
            type: String
        }
    }
}
</script>

