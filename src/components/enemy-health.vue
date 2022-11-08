<template>
    <div class="healthBar">
        <progress :value="enemy.health" max="100" class="styled">Determinate</progress>
    </div>
</template>

<script>
    export default {
        props: {
            enemy: Object,
        }
    }
</script>

<style lang="scss" scoped>
    progress.styled {
        display: block;
        width: 100%;
        height: 22px;
        border-bottom: 1px solid #000000;
    }
    progress.styled::-webkit-progress-bar {
        background-color: rgb(255, 255, 255);
    }
    progress.styled::-webkit-progress-value {
        background-color: rgb(255, 0, 0);
        background-image: linear-gradient(rgb(128, 0, 0), rgb(255, 0, 0));
    }
    progress.styled::-moz-progress-bar {
        background-color: rgb(255, 0, 0);
        background-image: linear-gradient(rgb(128, 0, 0), rgb(255, 0, 0));
    }
</style>