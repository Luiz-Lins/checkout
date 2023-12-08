<template>
  <div class="row justify-content-around">
    <div class="col-12">
      <select class="form-select form-select-lg mb-3" aria-label=".form-select-lg example">
        <option selected>Escolha um destino</option>
        <option v-for="destino in destinos" :value="destino.id" :key="destino.id">
          {{ destino.cidade }}
        </option>
      </select>
      <select class="form-select form-select-lg mb-3" aria-label=".form-select-lg example">
        <option selected>Selecione a origem</option>
        <option v-for="destino in destinos" :value="destino.id" :key="destino.id">
          {{ destino.cidade }}
        </option>
      </select>

      <div class="input-group mb-3">
        <span class="input-group-text" id="basic-addon1">Nome</span>
        <input
          type="text"
          class="form-control"
          placeholder="Principal passageiro"
          aria-label="Username"
          aria-describedby="basic-addon1"
        />
      </div>

      <div class="input-group mb-3">
        <input
          type="text"
          class="form-control"
          placeholder="Email do principal passageiro"
          aria-label="Recipient's username"
          aria-describedby="basic-addon2"
        />
        <span class="input-group-text" id="basic-addon2">@example.com</span>
      </div>

      <div class="input-group mb-3">
        <label class="input-group-text" for="inputGroupSelect01">Adultos</label>
        <select class="form-select" id="inputGroupSelect01">
          <option selected>Seleciona a quantidade</option>
          <option value="1">1</option>
          <option value="2">2</option>
          <option value="3">3</option>
          <option value="4">4</option>
          <option value="5">5</option>
        </select>
      </div>
      <div class="input-group mb-3">
        <label class="input-group-text" for="inputGroupSelect01">Crianças</label>
        <select class="form-select" id="inputGroupSelect01">
          <option selected>Seleciona a quantidade</option>
          <option value="1">1</option>
          <option value="2">2</option>
          <option value="3">3</option>
          <option value="4">4</option>
          <option value="5">5</option>
        </select>
      </div>
      <div class="form-check form-switch">
        <input class="form-check-input" type="checkbox" role="switch" id="flexSwitchCheckDefault">
        <label class="form-check-label" for="flexSwitchCheckDefault">Ida e volta</label>
      </div>
      <div class="input-group input-daterange">
          <input type="text" class="form-control" value="2012-04-05">
          <div class="input-group-addon">to</div>
          <input type="text" class="form-control" value="2012-04-19">
      </div>
      <div class="col-12">
        <button class="btn btn-primary" type="submit">Enviar Checkout</button>
      </div>
    </div>
  </div>
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
