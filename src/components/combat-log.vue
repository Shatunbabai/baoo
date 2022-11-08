<template>
    <div class="combatLogs">
        <p v-for="logs in combatLogs" :key="logs.index">
            {{logs}}
        </p>
    </div>
</template>

<script>
    export default {
        props: {
            combatLogs: Array,
        }
        
    }
</script>

<style lang="scss" scoped>
.combatLogs {
    width: 100%;
    height: 50px;
    border-bottom: 1px solid #000;
    overflow: hidden;
    padding: 5px;
    text-align: center;

    p {
        font-size: 12px;
    }
}
</style>