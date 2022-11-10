<template>
  <div id="demo">
      <div id="hero">  </div>
      <div id="enemy"> </div>
  </div>
</template>

<script>
  export default {
      props: {
          attackSpeed: Object,
      },
      data() {
          return {
              heroPosition: 0,
              enemyPosition: 104,
              interval: this.attackSpeed.attackSpeed / 5

          }
      },
      watch: {
          
      },

      created() {
          setInterval(() => {
              document.getElementById("hero").style.backgroundPosition = `-${this.heroPosition}px -87px`;
              document.getElementById("enemy").style.backgroundPosition = `-${this.enemyPosition}px 258px`;
              if (this.heroPosition < 420) {
                  this.heroPosition += 130
                  this.enemyPosition += 280
              } else {
                  this.heroPosition = 0
                  this.enemyPosition = 104
              }
          }, this.interval)
      },
      methods: {

      }
  }
</script>

<style lang="scss" scoped>
#demo {
  position: absolute;
  display: flex;
}

#hero {
  position: relative;
  left: 6px;
  top: 25px;
  height: 100px;
  width: 120px;
  background: 
  url('../assets/player_sprites.png') 0px -87px;
}

#enemy {
  position: relative;
  left: -50px;
  top: 20px;
  height: 100px;
  width: 140px;
  background: 
  url('../assets/enemy_sprite.png') 104px 258px;
}

// 140
</style>