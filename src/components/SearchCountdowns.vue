<template>
  <input
    type="text"
    v-model="search"
    placeholder="Search Countdowns"
    @keyup="emitGlobalKeyupSearch()"
  />
</template>

<script>
import EventBus from '@/components/EventBus'
export default {
  data() {
    return {
      search: ''
    }
  },
  methods: {
    emitGlobalKeyupSearch() {
      this.search
      EventBus.$emit('search-countdowns', this.search)
    }
  }
}
</script>

<style lang="scss" scoped>
input {
  font-size: 24px;
  border-radius: 20px;
  padding: 10px 20px;
  box-shadow: var(--shadow-base);
  color: rgba(var(--color-text-black), 1);
  grid-column: 1/3;

  @include breakpoint(lg) {
    grid-column: 1/2;
  }
}
</style>
