<template>
  <slot :open="onClick"> </slot>
</template>

<script setup lang="ts">
import { FilePicker } from '@apideck/file-picker-js';

const props = defineProps<{
  token: string;
  showAttribution?: boolean;
  onClose?: () => void;
  onReady?: () => void;
  onSelect?: (file: File) => void;
  onConnectionSelect?: (connection: any) => void;
  fileToSave?: File;
  title?: string;
  subText?: string;
}>();

function onClick() {
  FilePicker.open(props);
}
</script>

<script lang="ts">
export default {
  name: 'FilePicker',
};
</script>
