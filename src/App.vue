<template>
  <div>
    <Beverage :isIced="currentTemp === 'Cold'"/>
    <Base :baseColor="currentBase.color"/>
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
          <template v-for="base in bases" :key="base.id">
            <label>
              <input
                type="radio"
                name="base"
                :id="`r${base.id}`"
                :value="base.id"
                v-model="currentBase"
              />
              {{ base.name }}
          </label>
        </template>
      </li>
      <li>
        <template v-for="cream in creamers" :key="cream.id">
          <label>
            <input
              type="radio"
              name="cream"
              :id="`r${cream.id}`"
              :value="cream.id"
              v-model="currentCream"
            />
            {{ cream.name }}
          </label>
        </template>
      </li>
      <li>
        <template v-for="syrup in syrups" :key="syrup.id">
          <label>
            <input
              type="radio"
              name="syrup"
              :id="`r${syrup.id}`"
              :value="syrup.id"
              v-model="currentSyrup"
            />
            {{ syrup.name }}
          </label>
        </template>
      </li>
    </ul>
  </div>
</template>

<script setup lang="ts">
import Beverage from "./components/Beverage.vue";
import Base from "./components/Base.vue";
import { temps, currentTemp, bases, currentBase, creamers, currentCream, syrups, currentSyrup } from "./stores/beverage";
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
