<template>
    <div
        :class="`baseBeverage ${baseType.trim().toLowerCase().replace(/ /g, '')}`"
    ></div>
</template>

<script setup lang="ts">
type Props = {
    baseType: string;
};
defineProps<Props>();
</script>

<style scoped>
.baseBeverage {
    position: relative;
    width: 100%;
    height: 100%;
    bottom: 0;
    animation: pour-tea 2s;
    z-index: 300;
    /* border-radius: 0.05em 0.05em 2.2em 2.2em; */
}

.coffee {
    background: #3d2b1d;
}

.blacktea {
    background: #16100c;
}

.greentea {
    background: #293d13;
}
</style>
