<template>
  <div class="cell">
    <strong class="label">{{ label }}</strong>
    <slot :row="row">
      <span>
        {{ row[prop] ? row[prop] : "-" }}
      </span>
    </slot>
  </div>
</template>

<script>
export default {
  props: ["prop", "label"],
  data() {
    return {
      row: 0,
    };
  },
  mounted() {
    this.initialize();
  },
  methods: {
    initialize() {
      let rowIndex = this.$el.parentNode.getAttribute("data-row");
      this.row = this.$parent.data[rowIndex];
    },
  },
};
</script>

<style lang="scss" scoped>
.cell {
  text-align: left;
  margin-bottom: 1px;
  font-size: 11px;
  display: block;

  .label {
    background-color: #b5c6e1;
    padding: 0.5rem;
    display: inline-block;
    width: 25%;
    height: 100%;
  }
  span {
    padding: 0.5rem;
    width: 60%;
    display: inline-block;
    border-bottom: 1px solid #ccc;
    height: 100%;
  }
}
</style>