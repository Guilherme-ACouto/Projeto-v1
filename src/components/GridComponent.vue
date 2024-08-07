<template>
  <div class="grid">
    <table>
      <thead>
        <tr>
          <th v-for="col in columns" :key="col">{{ col }}</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(row, index) in data" :key="index">
          <td v-for="col in columns" :key="col">{{ row[col] }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: 'GridComponent',
  props: {
    columns: Array,
    data: Array
  }
};
</script>

<style scoped>
.grid {
  overflow-x: auto;
}

table {
  width: 100%; /* Ajustado para usar toda a largura disponível */
  border-collapse: collapse;
  font-size: 12px; /* Ajusta o tamanho da fonte conforme necessário */
}

th, td {
  border: 1px solid #ccc; /* Ajuste a espessura da borda conforme necessário */
  padding: 8px; /* Ajuste o padding conforme necessário */
  text-align: center;
  white-space: nowrap; /* Impede que o texto quebre para a linha seguinte */
}

thead th {
  background-color: #f4f4f4; /* Cor de fundo para o cabeçalho */
}
</style>