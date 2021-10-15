<template >
  <div class="memoMobileTable">
    <div v-if="data && data.length">
      <template v-for="(row, i) in data">
        <div :key="i" class="memoRow" :data-row="i">
          <slot name="default" :row="row"></slot>
          <div class="memoActions">
            <slot name="actions" :row="row"> Actions </slot>
          </div>
        </div>
      </template>
    </div>
    <div v-else>No hay datos para mostrar</div>
  </div>
</template>

<script>
export default {
  props: ["data"],
  data() {
    return {
      rowKey: 0,
    };
  },
  created() {
    this.initialize();
  },
  methods: {
    initialize() {},
    setRowKey(v) {
      this.rowKey = v;
    },
  },
};
</script>

<style lang="scss">
.memoMobileTable {
  .memoRow {
    margin-bottom: 8px;
    vertical-align: middle;

    .memoActions {
      position: sticky !important;
      top: 0;
      padding: 10px 0;
    }
  }
}
</style>