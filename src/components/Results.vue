<template>
  <p> {{score}} ms </p>
  <p class="speed"> {{speed}}</p>
</template>

<script>
export default {
props: ['score'],
data() {
    return {
        speed: null
    }
    
},
mounted() {
    if(this.score<250) {
        this.speed="Fast"
    }
    else if (this.score < 400) {
        this.speed = "Quite Fast"
    }
    else {
        this.speed = "Slow"
    }
}
}
</script>

<style>
p {
    margin-top: 40px;
}

.speed {
    font-size: 1.4em;
    color: rgb(0, 172, 106);
    font-weight: bold;
}
</style>