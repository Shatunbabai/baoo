<template>
  <div id="enemy-block">
      <p id="image">  </p>
  </div>
</template>

<script>
export default {
    data() {
        return {
            position: 0,
            interval: 100

        }
    },

    created() {
        setInterval(() => {
            document.getElementById("image").style.backgroundPosition = `-${this.position}px -87px`;
            if (this.position < 420) {
                this.position += 130
            } else {
                this.position = 0
            }
        }, this.interval)
    },
    methods: {

    }
}
</script>

<style lang="scss" scoped>
#image {
  height: 100px;
  width: 140px;
  background: 
  url('../assets/player_sprites.png') 0px -87px;
}

// 140
</style>