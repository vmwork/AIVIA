<template>
  <div class="ml-10 w-100">
    <div>
      <div class="w-25">
        <span>Size X</span>
        <v-text-field
          hide-details="auto"
          type="email"
          v-model="sizeX"
        ></v-text-field>
      </div>
      <div class="w-25">
        <span>Size Y</span>
        <v-text-field
          hide-details="auto"
          v-model="sizeY"
          type="email"
        ></v-text-field>
      </div>
    </div>
    <div class="block-box w-100 mt-10 d-flex flex-wrap">
      <div class="d-flex" v-for="block in setBlocks" :key="block">
        <div class="block block-1 mx-2 my-2"></div>
        <div class="block block-2 mx-2 my-2"></div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, computed } from "vue";
const sizeX = ref(0);
const sizeY = ref(0);

const firstBlock = ref(0);
const secondBlock = ref(0);

const setBlocks = computed(() => sizeX.value * sizeY.value);
</script>

<style lang="scss" scoped>
.block {
  width: 36px;
  height: 36px;
  background-color: white;
  cursor: pointer;
}
.block:hover {
  background-color: blue;
}
.block-box {
  background-color: black;
}
</style>
