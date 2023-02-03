<template>
  <main>
    <h1>Vue FilePicker</h1>

    <FilePicker
      :token="sessionJwt"
      :show-attribution="false"
      :on-close="onClose"
      :on-ready="onReady"
      :on-select="onSelect"
      v-slot="filePickerProps"
    >
      <button @click="filePickerProps.open">Open FilePicker</button>
    </FilePicker>
  </main>
</template>

<script setup lang="ts">
import FilePicker from '../src/FilePicker.vue';

const sessionJwt =
  'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJyZWRpcmVjdF91cmkiOiJodHRwczovL3BsYXRmb3JtLmFwaWRlY2suY29tL3ZhdWx0IiwiY29uc3VtZXJfbWV0YWRhdGEiOnsiYWNjb3VudF9uYW1lIjoiQXBpZGVjayBTYW5kYm94IiwidXNlcl9uYW1lIjoiSmFrZSIsImltYWdlIjoiaHR0cHM6Ly91bmF2YXRhci5pby9qYWtlQGFwaWRlY2suY29tIn0sInRoZW1lIjp7ImZhdmljb24iOiJodHRwczovL3d3dy5hcGlkZWNrLmNvbS9zdGF0aWMvZmF2aWNvbi5wbmciLCJwcmltYXJ5X2NvbG9yIjoiIzAzMDQ1ZSIsInByaXZhY3lfdXJsIjoiaHR0cHM6Ly9jb21wbGlhbmNlLmFwaWRlY2suY29tL3ByaXZhY3ktcG9saWN5Iiwic2lkZXBhbmVsX2JhY2tncm91bmRfY29sb3IiOiIjMTYyNjNmIiwic2lkZXBhbmVsX3RleHRfY29sb3IiOiIjRkZGRkZGIiwidGVybXNfdXJsIjoiaHR0cHM6Ly93d3cudGVybXNmZWVkLmNvbS90ZXJtcy1jb25kaXRpb25zLzk1N2M4NWMxYjA4OWFlOWUzMjE5YzgzZWZmNjUzNzdlIiwidmF1bHRfbmFtZSI6IkFwaWRlY2sgU2FuZGJveCJ9LCJzZXR0aW5ncyI6eyJzZXNzaW9uX2xlbmd0aCI6IjI0aCJ9LCJjb25zdW1lcl9pZCI6InRlc3QtY29uc3VtZXIiLCJhcHBsaWNhdGlvbl9pZCI6ImNmYVpyT1JnYUgyUE1RcEljalRwZmhFUklwSUVVSkhldjA5dWNqVHAiLCJzY29wZXMiOltdLCJpYXQiOjE2NzU0MTY4MjQsImV4cCI6MTY3NTUwMzIyNH0.hQUOQnlpD-fx304c_nxaffPDg9QVSjgJv3hi3_wIfvw';
const onSelect = (file: File) => {
  console.log('selected file:', file);
};

function onClose() {
  console.log('close!');
}

function onReady() {
  console.log('ready!');
}
</script>
