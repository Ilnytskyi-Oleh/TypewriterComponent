<script setup>

import TypewriterComponent from "./components/TypewriterComponent.vue";
import {generateRandomString} from "./helpers/stringHelpers.js";

const text = generateRandomString(50);
</script>

<template>
 <TypewriterComponent
     :text="text"
     text-class="test"
 />
</template>

<style scoped>
.test {
  color: #535bf2;
}
</style>
