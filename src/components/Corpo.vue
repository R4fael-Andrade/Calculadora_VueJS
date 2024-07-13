<script setup>
    const props =  defineProps(['getOperacao', 'valorn1', 'valorn2', 'tipoOperacao'])
</script>

<template>
    <div class="row">
        <h1 class="text-center">Calculadora <span>VueJS</span></h1>
      </div>
      <div class="row p-3">
        <div class="col-md-4">
          <input @keyup="props.valorn1" type="number" class="form-control">
        </div>
        <div class="col-md-4">
          <input  @keyup="props.valorn2"  type="number" class="form-control">
        </div>
        <div class="col-md-3">
          <select @change="props.tipoOperacao" class="form-control">
            <option value="somar">Somar</option>
            <option value="subtrair">Subtrair</option>
            <option value="multiplicar">Multiplicar</option>
            <option value="dividir">Dividir</option>
          </select>
        </div>
      </div>
      <div class="row mt-5">
       <p class="fs-5" >
        Resultado: {{ props.getOperacao }}
       </p>
      </div>
</template>

<style>
    .container {
    display: flex;
    flex-direction: column;
    height: 100vh;
    justify-content: center;
    text-align: center;
    align-items: center;
    }

    span {
    color: #00cc00;
    }

    input[type=number]::-webkit-inner-spin-button,
    input[type=number]::-webkit-outer-spin-button {
    -webkit-appearance: none;
    margin: 0;
}

.negativo {
    color: red;
}
</style>