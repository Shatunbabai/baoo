<template>
  <div id="app">
    <enemy-health-vue
    :enemy="enemy"
    ></enemy-health-vue>

    <hero-stats-vue
    :hero="hero"
    >
    </hero-stats-vue>

    <combat-log-vue
    :combatLogs="combatLogs"
    >
    </combat-log-vue>

    <enemy-block-vue>

    </enemy-block-vue>
  </div>
</template>

<script>
import enemyHealthVue from './components/enemy-health.vue';
import heroStatsVue from './components/hero-stats.vue';
import combatLogVue from './components/combat-log.vue';
import enemyBlockVue from './components/enemy-block.vue';

export default {
  components: {
    enemyHealthVue,
    heroStatsVue,
    combatLogVue,
    enemyBlockVue,
  },

  data() {
    return {
      enemy: {
        health: 97,
      },
      hero: {
        attack: 5,
        criticalChance: 0.1,
        criticalDamage: 1.5,
        attackSpeed: 5000,
      },
      combatLogs: [],
    }
  },

  created() {
    setInterval(() => {
      this.battle()

    }, this.hero.attackSpeed)
  },

  methods: {
    //main battle Scene
    battle() {
      let trueDamage = this.randomDamage(this.hero.attack / 2, this.hero.attack)
      this.enemy.health -= trueDamage
      this.combatlog(trueDamage, this.enemy.health)
    },

    // Random damage from min to max (example min 100/2, max 100 = damage from 50 to 100)
    randomDamage(min, max) {
      return Math.floor(Math.random() * (max-min+1) + min)
    },

    combatlog(damageInfo, enemyHealth) {
      if (this.combatLogs.length > 20) {
        this.combatLogs.pop()
        this.combatLogs.unshift(`You hit ${damageInfo} to enemy. Enemy have ${enemyHealth}`)
      } else {
        this.combatLogs.unshift(`You hit ${damageInfo} to enemy. Enemy have ${enemyHealth}`)
      }
    }
  }

}
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#app {
  width: 200px;
  height: 300px;
  margin: 10px;
  border: 1px solid #000;
}
</style>
