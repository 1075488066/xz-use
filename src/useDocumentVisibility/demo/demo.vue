<template>
  <div>isVisible: {{ isVisible }}</div>
</template>

<script lang="ts">
import { useDocumentVisibility } from 'xz-use';
import { watch } from 'vue';

export default {
  setup() {
    const { isVisible, visibilityState } = useDocumentVisibility();

    watch(visibilityState, () => {
      console.log('current visible state =  ' + visibilityState.value);
    });

    return {
      visibilityState,
      isVisible,
    };
  },
};
</script>
