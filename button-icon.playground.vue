<template>
  <span class="font-2-header text-color-1">
    BUTTON ICON
  </span>
  <div class="flex flex-row gap-4 p-4 bg-neutral-150 w-max border-dashed border-2 border-color-1 rounded-lg">
    <button-icon
      :icon="AddCircleOutlinedIcon"
      color="BLUE"
      @click="onClick"
    />

    <button-icon
      disabled
      color="BLUE"
      :icon="AddCircleOutlinedIcon"
    />

    <button-icon
      :icon="ChevronRightGradient1Icon"
      gradient
      big-icon
      color="BLUE"
      @click="onClick"
    />

    <button-icon
      disabled
      :icon="ChevronRightGradient1Icon"
      gradient
      color="BLUE"
      big-icon
    />

    <button-icon
      :icon="ChevronRightGradient2Icon"
      gradient
      big-icon
      color="VIOLET"
      @click="onClick"
    />

    <button-icon
      disabled
      :icon="ChevronRightGradient2Icon"
      gradient
      color="VIOLET"
      big-icon
    />

    <button-icon
      :icon="ChevronRightGradient3Icon"
      gradient
      big-icon
      color="ORANGE"
      @click="onClick"
    />

    <button-icon
      disabled
      :icon="ChevronRightGradient3Icon"
      gradient
      color="ORANGE"
      big-icon
    />

    <button-icon
      :icon="ClearIcon"
      color="WHITE"
      big-icon
      @click="onClick"
    />

    <button-icon
      disabled
      :icon="ClearIcon"
      big-icon
    />

    <button-icon
      :icon="ClearGradient1Icon"
      big-icon
      background
      gradient
      @click="onClick"
    />

    <button-icon
      disabled
      background
      :icon="ClearGradient1Icon"
      gradient
      big-icon
    />
  </div>
</template>

<script lang="ts" setup>
import ButtonIcon from '@/components/button-icon/button-icon.vue';

import AddCircleOutlinedIcon from '@/assets/icons/add-circle-outlined.svg?component';
import ClearGradient1Icon from '@/assets/icons/clear-gradient-1.svg?skipsvgo';
import ChevronRightGradient1Icon from '@/assets/icons/chevron-right-gradient-1.svg?skipsvgo';
import ChevronRightGradient2Icon from '@/assets/icons/chevron-right-gradient-2.svg?skipsvgo';
import ChevronRightGradient3Icon from '@/assets/icons/chevron-right-gradient-3.svg?skipsvgo';
import ClearIcon from '@/assets/icons/clear.svg?component';

function onClick() {
  // eslint-disable-next-line no-alert
  alert("Los Angeles' full name is \"El Pueblo de Nuestra Senora la Reina de los Angeles de Porciuncula\"");
}
</script>
