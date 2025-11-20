<template>
  <div>
    <div class="flex justify-between pb-1">
      <p>Cultivar</p>
      <p>Failure Rate</p>
    </div>

    <div class="flex flex-column gap-2">
      <div class="failed-cultivar-container" @click="openMassDialog">
        <div class="flex justify-between">
          <div class="flex items-center gap-1">
            <p>KBSC</p>
            <font-awesome-icon icon="fa-solid fa-angle-right" />
          </div>
          <p>11%</p>
        </div>

        <div class="pt-05">
          <div class="failure-bar"></div>
        </div>
      </div>
      <div class="failed-cultivar-container" @click="openMassDialog">
        <div class="flex justify-between">
          <div class="flex items-center gap-1">
            <p>KBSC</p>
            <font-awesome-icon icon="fa-solid fa-angle-right" />
          </div>
          <p>11% test</p>
        </div>

        <div class="pt-05">
          <div class="failure-bar"></div>
        </div>
      </div>
      <div class="failed-cultivar-container" @click="openMassDialog">
        <div class="flex justify-between">
          <div class="flex items-center gap-1">
            <p>KBSC</p>
            <font-awesome-icon icon="fa-solid fa-angle-right" />
          </div>
          <p>11%</p>
        </div>

        <div class="pt-05">
          <div class="failure-bar"></div>
        </div>
      </div>
    </div>

    <!-- <Button label="Open Cultivar Mass Performance" @click="openMassDialog" />
    <Button label="Close" @click="closeDialog" /> -->
  </div>
</template>

<script setup lang="ts">
import { inject } from "vue";
import { Button } from "primevue";
import { useDialog } from "primevue/usedialog";
import CultivarMassPerformance from "./CultivarMassPerformance.vue";

const dialogRef: any = inject("dialogRef");
const dialog = useDialog();

const openMassDialog = () => {
  dialog.open(CultivarMassPerformance, {
    props: {
      header: "Dialog B",
      modal: true,
      style: { width: "30vw" },
    },
    data: {
      parentInfo: "Data from cultivar breakdown",
    },
    onClose: (options) => {
      if (options?.data) {
        console.log("mass performance returned:", options.data);
      }
    },
  });
};

</script>

<style scoped lang="scss">
.failure-bar {
  height: 10px;
  background-color: red;
  border-radius: 10px;
}

.failed-cultivar-container {
  cursor: pointer;
  padding: 10px;

  &:hover {
    border-radius: 4px;
    background-color: var(--p-green-50);
    font-weight: bold;
  }
}
</style>
