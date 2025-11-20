<script setup lang="ts">
import "../../style.css";
import { Card, useDialog } from "primevue";
import CultivarBreakdown from "./dialogs/CultivarBreakdown.vue";

const dialog = useDialog();

const openCultivarBreakdown = () => {
  dialog.open(CultivarBreakdown, {
    props: {
      header: "Cultivar Breakdown",
      modal: true,
      style: { width: "25vw" },
    },
    data: {
      userId: 123,
      someOtherData: "example",
    },
    onClose: (options) => {
      if (options?.data) {
        console.log("Dialog A returned:", options.data);
      }
    },
  });
};
</script>

<template>
  <Card>
    <template #title>
      <span class="font-800 text-2xl">MY-SL01</span>
    </template>
    <template #content>
      <div class="grid grid-cols-2 items-center gap-1 py-1">
        <div class="yield-card">
          <p class="yield-card__text p-0">Actual</p>
          <p class="yield-card__text--bold">708 heads</p>
        </div>
        <!-- <div class="yield-card failed-yield" @click="visible = true"> -->
        <div class="yield-card failed-yield" @click="openCultivarBreakdown">
          <p class="yield-card__text p-0">Failed</p>
          <p class="yield-card__text--bold">708 heads</p>
        </div>
      </div>
      <div class="mass-summary flex justify-between items-center">
        <p class="mass-summary__text">Mass Summary</p>
        <div class="flex flex-column gap-1">
          <p>9.7kg</p>
          <p>9700g</p>
        </div>
      </div>
      <div class="grid grid-cols-3 gap-1">
        <div class="farm-parameters">
          <div class="icon-wrapper">
            <font-awesome-icon icon="fa-solid fa-bolt" />
          </div>
          <p>EC</p>
          <p class="font-800 text-lg">1.9</p>
        </div>
        <div class="farm-parameters">
          <div class="icon-wrapper">
            <font-awesome-icon icon="fa-solid fa-droplet" />
          </div>
          <p>pH</p>
          <p class="font-800 text-lg">1.9</p>
        </div>
        <div class="farm-parameters">
          <div class="icon-wrapper">
            <font-awesome-icon icon="fa-solid fa-wind" />
          </div>
          <p>CO2</p>
          <p class="font-800 text-lg">1.9</p>
        </div>
      </div>
    </template>
  </Card>
  <!-- <Dialog
    v-model:visible="visible"
    modal
    header="Cultivar Performance"
    :style="{ width: '25rem' }"
  >
    <div class="flex justify-between pb-1">
      <p>Cultivar</p>
      <p>Failure Rate</p>
    </div>

    <div class="flex flex-column gap-2">
      <div class="failed-cultivar-container">
        <div class="flex justify-between">
          <p>KBSC</p>
          <p>11%</p>
        </div>

        <div class="pt-05">
          <div class="failure-bar"></div>
        </div>
      </div>
      <div class="failed-cultivar-container">
        <div class="flex justify-between">
          <p>LTRP</p>
          <p>11%</p>
        </div>

        <div class="pt-05">
          <div class="failure-bar"></div>
        </div>
      </div>
      <div class="failed-cultivar-container">
        <div class="flex justify-between">
          <p>KRRS</p>
          <p>11%</p>
        </div>

        <div class="pt-05">
          <div class="failure-bar"></div>
        </div>
      </div>
    </div>
  </Dialog> -->
</template>

<style scoped lang="scss">
.mass-summary {
  background-color: var(--p-green-50);
  border-radius: 4px;
  padding: 1rem;
  border: 1px solid var(--p-green-200);
  margin-bottom: 0.5rem;

  &__text {
    font-weight: 600;
    font-size: 1rem;
  }
}

.yield-card {
  background-color: var(--p-green-50);
  border-radius: 4px;
  padding-inline: 1rem;

  &__text {
    font-size: 1rem;
    padding-block: 0.8rem;

    &--bold {
      font-weight: bold;
      font-size: 1.25rem;
      padding-bottom: 1rem;
    }
  }
}

.failed-yield {
  cursor: pointer;

  &:hover {
    background-color: var(--p-green-100);
  }
}

.farm-parameters {
  border-radius: 4px;
  padding: 1rem;
  border: 1px solid var(--p-green-200);

  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 0.5rem;
}

.icon-wrapper {
  background-color: var(--p-green-100);
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 40px;
  height: 40px;
  border-radius: 50%;
}

.failure-bar {
  height: 10px;
  background-color: red;
  border-radius: 10px;
}
</style>
