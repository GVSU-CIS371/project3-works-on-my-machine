<template>
    <Mug>
        <Cold v-if="isIced" />
        <Hot v-else />
        <Contents>
            <template v-slot:top>
                <Creamer
                    :creamType="userCream"
                    v-if="userCream !== 'No Cream'"
                />
            </template>
            <template v-slot:mid v-if="userSyrup !== 'No Syrup'">
                <Syrup :syrupType="userSyrup" />
            </template>
            <template v-slot:bottom>
                <Base :baseType="userBase" />
            </template>
        </Contents>
    </Mug>
</template>
<script setup lang="ts">
import Contents from "./Contents.vue";
import Mug from "./Mug.vue";
import Syrup from "./Syrup.vue";
import Base from "./Base.vue";
import Creamer from "./Creamer.vue";
import Hot from "./Hot.vue";
import Cold from "./Cold.vue";

type Props = {
    isIced: boolean;
    userCream: string;
    userSyrup: string;
    userBase: string;
};
defineProps<Props>();
</script>
