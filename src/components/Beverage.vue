<template>
  <Mug>
    <Cold v-if="isIced" />
    <Hot v-else />
    <Contents>
      <template v-slot:top>
        <Creamer v-if="creamer.id !== 'c1'" :cream-color="creamer.color"/>
      </template>
      <template v-slot:mid>
        <Syrup v-if="syrup.id !== 's1'" :syrup-color="syrup.color"/>
      </template>
      <template v-slot:bottom>
        <Base :base-color="base.color" />
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
  base: {id: string; color: string };
  creamer: { id: string; color: string };
  syrup: { id: string; color: string };
  /*isBlack: boolean;
  isGreen: boolean;
  isCoffee: boolean;
  isMilk: boolean;
  isCream: boolean;
  ishalf: boolean;
  isVanilla: boolean;
  isCaramel: boolean;
  isHazelnut: boolean;*/
};
defineProps<Props>();
</script>
