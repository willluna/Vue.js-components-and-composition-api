<template>
  <div>{{ fullName }}</div>
</template>

<script>
import { toRefs, computed } from "vue";

export default {
  props: {
    name: String,
    lastName: String,
  },
  setup(props, { expose }) {
    console.log(context);

    const { name, lastName } = toRefs(props);

    const fullName = computed(() => {
      return `${name.value} ${lastName.value}`;
    });

    expose({
      fullName,
    });

    return {
      fullName,
    };
  },
};
</script>
