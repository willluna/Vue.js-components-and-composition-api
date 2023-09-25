<template>
  <div>fullName: {{ fullName }}</div>
</template>

<script>
import { ref, computed } from "vue";

export default {
  setup() {
    const name = ref("Will");
    const lastName = ref("Luna");

    const fullName = computed(() => {
      return `${name.value} ${lastName.value}`;
    });

    return {
      fullName,
    };
  },
};
</script>
