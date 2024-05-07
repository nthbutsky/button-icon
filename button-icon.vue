<template>
  <button
    class="w-fit justify-start items-center inline-flex focus:outline-color-1"
    :class="{
      'cursor-not-allowed': disabled,
      'bg-neutral-100 rounded-full': background,
    }"
    :type="isForm"
    :disabled="disabled"
    :form="formId"
    v-bind="$attrs"
    @click="onClick"
  >
    <component
      :is="icon"
      v-if="icon"
      :class="{
        'hover:text-color-2 text-color-1': !disabled && color === 'BLUE',
        'lg:hover:text-color-1-5 text-neutral-100': color === 'WHITE',
        'text-neutral-400': disabled,
        'w-6 h-6': !bigIcon,
        'w-10 h-10': bigIcon,
        'gradient1-disabled': gradient && disabled && color === 'BLUE',
        'gradient1-hovered': gradient && !disabled && color === 'BLUE',
        'gradient2-disabled': gradient && disabled && color === 'VIOLET',
        'gradient2-hovered': gradient && !disabled && color === 'VIOLET',
        'gradient3-disabled': gradient && disabled && color === 'ORANGE',
        'gradient3-hovered': gradient && !disabled && color === 'ORANGE',
      }"
    />
  </button>
</template>

<script lang="ts" setup>
import {
  FunctionalComponent, SVGAttributes, computed,
} from 'vue';

import {
  TColorScheme, COLOR_SCHEME,
} from '@/types/color-scheme';

import colorDesignTokens from '@/design-tokens/color.json';

interface IProps {
  color?: TColorScheme;
  icon?: FunctionalComponent<SVGAttributes>;
  disabled?: boolean;
  formId?: string;
  background?: boolean;
  gradient?: boolean;
  bigIcon?: boolean;
}

const props = withDefaults(defineProps<IProps>(), {
  color: COLOR_SCHEME.BLUE,
  icon: undefined,
  disabled: false,
  formId: undefined,
  background: false,
  gradient: false,
  bigIcon: false,
});

const isForm = computed(() => {
  return props.formId ? 'submit' : 'button';
});

const gradient1Disabled = colorDesignTokens['neutral-400'];
const gradient1Hovered = colorDesignTokens['color-2'];
const gradient2Disabled = colorDesignTokens['neutral-400'];
const gradient2Hovered = colorDesignTokens['color-3'];
const gradient3Disabled = colorDesignTokens['neutral-400'];
const gradient3Hovered = colorDesignTokens['color-4'];

// eslint-disable-next-line func-call-spacing, no-spaced-func
const emits = defineEmits<{
  (e: 'click'): void;
}>();

function onClick() {
  emits('click');
}
</script>

<style lang="css">
.gradient1-disabled path {
  fill: v-bind(gradient1Disabled);
}

.gradient1-hovered:hover path {
  fill: v-bind(gradient1Hovered);
}

.gradient2-disabled path {
  fill: v-bind(gradient2Disabled);
}

.gradient2-hovered:hover path {
  fill: v-bind(gradient2Hovered);
}

.gradient3-disabled path {
  fill: v-bind(gradient3Disabled);
}

.gradient3-hovered:hover path {
  fill: v-bind(gradient3Hovered);
}
</style>
