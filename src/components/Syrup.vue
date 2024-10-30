<template>
    <div
        :class="`syrup ${syrupType.trim().toLowerCase().replace(/ /g, '')}`"
    ></div>
</template>

<script setup lang="ts">
type Props = {
    syrupType: string;
};
defineProps<Props>();
</script>
<style lang="scss" scoped>
.syrup {
    transform: translateY(400%);
    background-color: #c6c6c6;
    position: relative;
    width: 100%;
    height: 20%;
    animation: pour-tea 2s 1s forwards;
    z-index: 2;
}

.vanilla {
    background-color: #f3e5ab;
}

.caramel {
    background-color: #d4a24f;
}

.hazelnut {
    background-color: #b37f4d;
}
</style>
