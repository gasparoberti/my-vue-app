<script setup lang="ts">
import { ref } from "vue"

const periods = ["Today", "This Week", "This Month"]

const selectedPeriod = ref("Today")

function selectPeriod(period: string) {
    // console.log(period);
    selectedPeriod.value = period
}
</script>

<template>
    <nav class="is-primary panel">
        {{ selectedPeriod }}
        <span class="panel-tabs">
            <a v-for="period of periods" :key="period" v-bind:class="{ 'is-active': period === selectedPeriod }"
                v-on:click="selectPeriod(period)">
                {{ period }}
            </a>
        </span>
    </nav>
</template>

<style>

</style>