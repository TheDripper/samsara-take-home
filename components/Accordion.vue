<template>
  <div 
    :class="`${content.classes}`"
    class="list-item px-4"
    @click="toggle"
  >
    <div 
      class="flex justify-between items-center py-4"
    >
      <div 
        class="py-6 item-content"
        v-html="content.listItem"
      />
      <span 
        v-if="content.accordionText"
        class="icon"
      >
        <h1
          v-if="open"
        >-</h1>
        <h1
          v-if="!open"
        >+</h1>
      </span>
    </div>
    <div v-if="open && content.accordionText">
      <div 
        class="h2-left-black pb-4"
        v-html="content.accordionText"
      />
    </div>
  </div>
</template>
<script>
export default {
  props: {
    content: {
      type: Object,
      default: () => {}
    }
  },
  data() {
    return {
      open: false
    }
  },
  methods: {
    toggle() {
      this.open = !this.open
    }
  }
}
</script>
<style scoped lang="scss">
.list-item {
  cursor: pointer;
  @apply flex flex-col justify-between mx-auto border-t relative;
  width: calc(100% - 4rem);
  max-width: 714px;
  border-color: #00263E;
  &:last-child {
    @apply border-b;
  }
}
.icon {
  transition: 0.2s transform ease;
  color: #00263E;
  font-size: 3rem;
  font-weight: 200;
  @apply relative;
  .accordion--open & {
    transform: rotate(180deg);
  }
}
</style>
