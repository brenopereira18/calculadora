<script setup>
  const props = defineProps(['campo1', 'campo2', 'operacao' , 'selecionaOperador'])
</script>

<template>
  <section class="section-calculos rounded-4">
    <div class="row">
      <div class="col-2">
        <input
          @change="props.campo1"
          type="number"
          class="form-control"
        />
      </div>
      <div class="col-1">
        <select
          @change="props.operacao"
          class="form-control text-center"
        >
          <option value="+">+</option>
          <option value="-">-</option>
          <option value="x">x</option>
          <option value="/">/</option>
        </select>
      </div>
      <div class="col-2">
        <input
          @change="props.campo2"
          type="number"
          class="form-control"
        />
      </div>
      <div class="col-1 p-0 m-2">
        <span>=</span>
      </div>
      <div class="col-2 campo-resultado">
        <span>{{ props.selecionaOperador }}</span>
      </div>
    </div>
  </section>
</template>

<style scoped>

  .section-calculos {
    background-color: #C9D7DD;
    padding: 100px;
  }

  .campo-resultado {    
    font-size: 32px;
    text-align: center;
  }

  .row {
    height: 100px;
    align-items: center;
  }   
  
</style>