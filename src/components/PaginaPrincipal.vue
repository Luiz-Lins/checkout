<template>
  <form class="row g-3">
    <div class="input-group input-daterange">
        <input type="text" placeholder="data de ida" class="form-control" value="" required>
        <div class="input-group-addon">to</div>
        <input type="text" placeholder="data de volta" class="form-control" value="" required>
    </div>
    <div class="col-md-6">
      <div class="input-group">
        <input type="text" placeholder="Adultos" class="form-control" id="validationDefaultUsername"  aria-describedby="inputGroupPrepend2">
          <select class="form-control" id="inputGroupSelect01">
            <option selected>Seleciona a quantidade</option>
            <option value="1">1</option>
            <option value="2">2</option>
            <option value="3">3</option>
            <option value="4">4</option>
            <option value="5">5</option>
          required </select>
      </div>
    </div>
    <div class="col-md-6">
      <div class="input-group">
        <input type="text" placeholder="Crianças" class="form-control" id="validationDefaultUsername"  aria-describedby="inputGroupPrepend2">
          <select class="form-control" id="inputGroupSelect01">
            <option selected>Seleciona a quantidade</option>
            <option value="1">1</option>
            <option value="2">2</option>
            <option value="3">3</option>
            <option value="4">4</option>
            <option value="5">5</option>
          </select>
      </div>
    </div>
    <div class="col-md-12">
      <select class="form-select form-select-lg mb-3" aria-label=".form-select-lg example">
        <option selected>Selecione a origem</option>
        <option v-for="destino in destinos" :value="destino.id" :key="destino.id">
          {{ destino.cidade }}
        </option>
      required </select>
      <select class="form-select form-select-lg mb-3" aria-label=".form-select-lg example">
        <option selected>Escolha um destino</option>
        <option v-for="destino in destinos" :value="destino.id" :key="destino.id">
          {{ destino.cidade }}
        </option>
      </select>
    </div>
    <div class="col-md-12">
      <div class="input-group">
        <input type="text" placeholder="Nome do principal passageiro" class="form-control" id="validationDefaultUsername"  aria-describedby="inputGroupPrepend2" required>
      </div>
    </div>
    <div class="col-md-12">
      <div class="input-group">
        <input type="text" placeholder="Email do principal passageiro" class="form-control" id="validationDefaultUsername"  aria-describedby="inputGroupPrepend2" required>
      </div>
    </div>
    <div class="col-12">
      <div id="liveAlertPlaceholder">
        <button class="btn btn-primary" id="liveAlertBtn" type="submit">Enviar Checkout</button>
      </div>
    </div>
  </form>
</template>

<style>
.fundo1 {
  background-color: rgb(131, 131, 231);
}
</style>

<script>
//http://localhost:3000/destinos

export default {
  data: () => {
    return {
      destinos: []
    }
  },
  mounted() {
    this.getDestinos()
  },
  methods: {
    getDestinos() {
      fetch('http://localhost:3000/destinos')
        .then((response) => response.json())
        .then((destinos) => {
          this.destinos = destinos
        })
    }
  }
}
</script>


