<template>
    <div class="heroStats">
        <p>Dmg: <br> {{hero.attack}}</p>
        <p>Speed: <br> {{hero.attackSpeed}}</p>
        <p>Crit (%/Dmg): <br> {{hero.criticalChance}} / {{hero.criticalDamage}}</p>
    </div>
</template>

<script>
    export default {
        props: {
            hero: Object,
        }
        
    }
</script>

<style lang="scss" scoped>
.heroStats {
    width: 100%;
    height: 30px;
    border-bottom: 1px solid #000;
    padding: 3px;
    display: flex;
    justify-content: space-around;
    align-items: center;

    p {
        font-size: 10px;
        margin-left: 5px;
    }
}

</style>