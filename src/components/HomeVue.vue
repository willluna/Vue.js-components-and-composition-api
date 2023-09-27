<template>
  <div>{{ fullName }}</div>
  <div>{{ userName }}</div>
  <button ref="btn">Click!</button>
</template>

<script>
import { ref, toRefs, computed, inject, watch } from "vue";

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

    const btn = ref(null);

    console.log(btn.value);

    watch(btn, (valor) => {
      console.log(valor);
    });

    return {
      fullName,
      userName,
      btn,
    };
  },
};
</script>
