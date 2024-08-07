<template>
  <div class="filtro">
    <fieldset class="filtro-fieldset">
      <legend class="filtro-legend">Exibe Fardos ou Bobinas Retornados do PA:</legend>
      <div class="radio-group">
        <label>
          <input type="radio" value="bobinas" v-model="selectedType" @change="emitChange">
          Bobinas
        </label>
        <label>
          <input type="radio" value="fardos" v-model="selectedType" @change="emitChange">
          Fardos
        </label>
      </div>
    </fieldset>
  </div>
</template>

<script>
export default {
  name: 'FiltroComponent',
  data() {
    return {
      selectedType: 'bobinas' // Valor inicial
    };
  },
  methods: {
    emitChange() {
      this.$emit('filter-change', this.selectedType);
    }
  }
};
</script>

<style scoped>
.filtro {
  margin-bottom: 20px;
}

.filtro-fieldset {
  border: 2px solid #696969; /* Cor e espessura da borda */
  padding: 10px; /* Espaçamento interno para não envolver o texto */
  margin: 0;
  border-radius: 4px; /* Bordas arredondadas */
}

.filtro-legend {
  font-weight: bold;
  color: #000000;
  padding: 0 5px;
  margin-bottom: 10px; /* Espaçamento entre o texto e os radio buttons */
  display: inline-block; /* Para evitar que a borda seja cortada ao redor do texto */
}

.radio-group {
  display: flex;
  gap: 10px; /* Espaço entre os radio buttons */
}
</style>
