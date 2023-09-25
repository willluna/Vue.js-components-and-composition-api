<template>
  <div>{{ fullName }}</div>
  <div>{{ userName }}</div>
</template>

<script>
import { toRefs, computed, inject } from "vue";

export default {
  props: {
    name: String,
    lastName: String,
  },
  setup(props, { expose }) {
    const { name, lastName } = toRefs(props);

    const fullName = computed(() => {
      return `${name.value} ${lastName.value}`;
    });

    const userName = inject("userName");

    expose({
      fullName,
    });

    return {
      fullName,
      userName,
    };
  },
};
</script>
