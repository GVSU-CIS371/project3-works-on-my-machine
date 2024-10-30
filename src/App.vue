<template>
    <div>
        <Beverage
            :isIced="currentTemp === 'Cold'"
            :userCream="currentCreamer"
            :userSyrup="currentSyrup"
            :userBase="currentBase"
        />
        <ul>
            <li>
                <template v-for="temp in temps" :key="temp">
                    <label>
                        <input
                            type="radio"
                            name="temperature"
                            :id="`r${temp}`"
                            :value="temp"
                            v-model="currentTemp"
                        />
                        {{ temp }}
                    </label>
                </template>
            </li>
            <li>
                <template v-for="base in bases" :key="base">
                    <label>
                        <input
                            type="radio"
                            name="base"
                            :id="`r${base}`"
                            :value="base"
                            v-model="currentBase"
                        />
                        {{ base }}
                    </label>
                </template>
            </li>
            <li>
                <template v-for="cream in creams" :key="cream">
                    <label>
                        <input
                            type="radio"
                            name="cream"
                            :id="`r${cream}`"
                            :value="cream"
                            v-model="currentCreamer"
                        />
                        {{ cream }}
                    </label>
                </template>
            </li>
            <li>
                <template v-for="syrup in syrups" :key="syrup">
                    <label>
                        <input
                            type="radio"
                            name="syrup"
                            :id="`r${syrup}`"
                            :value="syrup"
                            v-model="currentSyrup"
                        />
                        {{ syrup }}
                    </label>
                </template>
            </li>
        </ul>
    </div>
</template>

<script setup lang="ts">
import { ref } from "vue";
import Beverage from "./components/Beverage.vue";

// Define reactive data
const temps = ref(["Hot", "Cold"]);
const bases = ref(["Black Tea", "Green Tea", "Coffee"]);
const creams = ref(["No Cream", "Milk", "Cream", "Half & Half"]);
const syrups = ref(["No Syrup", "Vanilla", "Caramel", "Hazelnut"]);

const currentTemp = ref("Hot");
const currentCreamer = ref("No Cream");
const currentSyrup = ref("No Syrup");
const currentBase = ref("Black Tea");
</script>

<style lang="scss">
body,
html {
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100%;
    background-color: #6e4228;
    background: linear-gradient(to bottom, #6e4228 0%, #956f5a 100%);
}
ul {
    list-style: none;
}
</style>
