<template>
  <div v-if="isMobile">
    <mobile-table :data="paginatedData">
      <Cell prop="id" label="Id:"></Cell>
      <Cell prop="created_at" label="Fecha:"></Cell>
      <Cell prop="folio" label="Folio:"></Cell>
      <Cell prop="eco" label="Núm. Económico:"></Cell>
      <Cell prop="user.name" label="Asignado a:"></Cell>
      <Cell prop="customer.name" label="Cliente:"></Cell>
      <Cell prop="movement.name" label="Movimiento:"></Cell>
      <Cell prop="brige.name" label="Puente:"></Cell>
      <Cell prop="origen" label="Origen"></Cell>
      <Cell prop="destino" label="Destino"></Cell>
      <Cell prop="num_integracion" label="# Integración"></Cell>
      <Cell prop="num_inbond" label="# Inbond"></Cell>
      <Cell prop="salida_base" label="Salida base">
        <template v-slot="scope">
            <el-button
              type="info"
              size="mini"
              @click="accion1(scope.row.id)"
            >
              Accion
            </el-button>
        </template>
      </Cell>
      </template>
    </mobile-table>
  </div>
</template>

<script>
import MobileTable from "../MobileTable.vue";
import Cell from "../MobileTableCell.vue";

export default {
  components: {
    MobileTable,
    Cell,
  },
  methods: {
    accion1(id) {
      console.log(id);
    },
  },
};
</script>

<style>
</style>