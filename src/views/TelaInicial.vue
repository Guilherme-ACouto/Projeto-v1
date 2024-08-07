<template>
  <div class="tela-inicial">
    <div class="buttons">
      <button @click="buscar">Buscar</button>
      <button @click="exportarExcel">Excel</button>
      <button @click="exportarPDF">PDF</button>
    </div>
    <FiltroComponent @filter-change="handleFilterChange" />
    <GridComponent :columns="columns" :data="filteredData" />
  </div>
</template>

<script>
import FiltroComponent from "@/components/FiltroComponent.vue";
import GridComponent from "@/components/GridComponent.vue";

export default {
  components: {
    FiltroComponent,
    GridComponent
  },
  data() {
    return {
      selectedType: "bobinas",
      columnsBobinas: [
        "bobina", "bobina mae", "sta. atual", "sta. sit. atual", 
        "sta. PA volume", "contr. reg", "patio", "pilha", 
        "data atualização", "qtd. dia", "ponto entrega", 
        "dt. liberacao", "qtd. dia", "dt. rendimento", "qtd. dia", 
        "dt. entrada no pa", "qtd. dia", "usuario"
      ],
      columnsFardos: [
        "Num Fardo", "Fardo Pai", "Sta. Atual", "Sta. Sit. Atual", 
        "Sta. PA Vaolume", "Contr. Reg. Elim.", "Pátio", "Pilha", 
        "Dt. Atualização", "Qtd. Dia", "Sigla Atual", "Cód. Clas. Qual.", 
        "Dt. Conf. Embalagem", "Qtd. Dia", "Dt. Lib. Inspeção", "Qtd. Dia", 
        "Dt. Rendimento", "Dt. Dia", "Dt. Entrada no PA", "Qtd. Dia", "Usuário"
      ],
      dataBobinas: [], // Dados das bobinas
      dataFardos: [] // Dados dos fardos
    };
  },
  computed: {
    columns() {
      return this.selectedType === "bobinas" ? this.columnsBobinas : this.columnsFardos;
    },
    filteredData() {
      return this.selectedType === "bobinas" ? this.dataBobinas : this.dataFardos;
    }
  },
  methods: {
    handleFilterChange(type) {
      this.selectedType = type;
    },
    buscar() {
      // lógica para buscar dados
    },
    exportarExcel() {
      // lógica para exportar dados para Excel
    },
    exportarPDF() {
      // lógica para exportar dados para PDF
    }
  }
};
</script>

<style scoped>
.tela-inicial {
  padding: 12px;
  display: flex;
  flex-direction: column; /* Organiza os elementos em coluna */
}

.buttons {
  margin-bottom: 30px; /* Espaçamento abaixo dos botões */
}

button {
  margin-right: 10px;
  padding: 10px 5px;
}
</style>
