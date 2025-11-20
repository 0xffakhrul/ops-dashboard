<template>
  <div>
    <p>This is mass performance (nested)</p>
    <p>Received from parent: {{ dialogData.parentInfo }}</p>

    <Button label="Confirm" @click="confirm" />
    <Button label="Cancel" @click="cancel" />
  </div>
</template>

<script setup lang="ts">
import { inject } from "vue";

const dialogRef: any = inject("dialogRef");
const dialogData = dialogRef.value.data;

const confirm = () => {
  dialogRef.value.close({
    confirmed: true,
    data: "result from Dialog B",
  });
};

const cancel = () => {
  dialogRef.value.close();
};
</script>
