<template>
  <button :class="buttonClass">
    {{ text }}
  </button>
</template>

<script>
export default {
  name: "ActionButton",
  props: {
    text: {
      type: String,
      required: true,
    },
    type: {
      type: String,
      required: false,
      default: "primary",
      validator(value) {
        return ["primary", "secondary"].includes(value);
      }
    }
  },
  computed: {
    buttonClass() {
      return {
        [this.type]: true,
      }
    }
  }
};
</script>

<style scoped>
button {
  @apply px-5 py-3 font-medium;
}

.primary {
  @apply text-white border-0 rounded bg-brand-blue-1;
}

.secondary {
  @apply text-brand-blue-2 bg-transparent
}
</style>