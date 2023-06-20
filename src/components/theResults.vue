<template>
  <p class="time">Your reaction time = {{score}} milliseconds</p>
  <p class="rank">{{rank}}</p>
</template>

<script>
export default {
    props: ['score'],
    data () {
        return{
           rank: null
        }
    },
}
</script>

<style>
.time {
  background-color: #15202b;
  color: #fff;
  padding: 20px;
  font-size: 24px;
  text-align: center;
  position: relative;
}

</style>
