<template>
  <div id="app">
    <Navbar></Navbar>
    <bitcoincard :btc="btc" :eth="eth" :xrp="xrp"></bitcoincard>
    <div id="rect">
      <b-container id="box">
        <b-row id="square">
          <b-col cols="12" md="12" offset-md="0">
            <div
              id="column"
            >La criptomoneda, criptodivisa (del inglés cryptocurrency) o criptoactivo es un medio digital de intercambio que utiliza criptografía fuerte para asegurar las transacciones financieras, controlar la creación de unidades adicionales y verificar la transferencia de activos.</div>
          </b-col>
        </b-row>
      </b-container>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import Navbar from "./components/Navbar.vue";
import Bitcoincard from "./components/Bitcoincard.vue";

export default {
  name: "app",
  components: {
    Navbar,
    Bitcoincard
  },
  data() {
    return {
      btc: {
        time: String,
        asset_id_base: String,
        asset_id_quote: String,
        rate: Number
      },
      xrp: {
        time: String,
        asset_id_base: String,
        asset_id_quote: String,
        rate: Number
      },
      eth: {
        time: String,
        asset_id_base: String,
        asset_id_quote: String,
        rate: Number
      }
    };
  },
  mounted() {
    this.getCoins();
  },
  methods: {
    getCoins() {
      axios
        .get(
          "https://rest.coinapi.io/v1/exchangerate/BTC/USD?apikey=7AC64146-C9AA-478A-AB2B-E953ED16480F"
        )
        .then(response => {
          this.btc = response.data;
        })
        .catch(e => console.log(e));

      axios
        .get(
          "https://rest.coinapi.io/v1/exchangerate/ETH/USD?apikey=7AC64146-C9AA-478A-AB2B-E953ED16480F"
        )
        .then(response => {
          this.eth = response.data;
        })
        .catch(e => console.log(e));
      axios
        .get(
          "https://rest.coinapi.io/v1/exchangerate/XRP/USD?apikey=7AC64146-C9AA-478A-AB2B-E953ED16480F"
        )
        .then(response => {
          this.xrp = response.data;
        })
        .catch(e => console.log(e));
    }
  }
};
</script>

<style lang="scss">
$color_1: #2c3e50;
$font_family_1: "Avenir", Helvetica, Arial, sans-serif;

#app {
  font-family: $font_family_1;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: $color_1;
  margin-top: 0px;
}
#rect {
  margin-top: 40px;
  margin-bottom: 20px;
  height:200px;
}
#column {
  background-color: salmon;
  padding: 0px;
  border-radius: 5px;
  color:black;
  height:150px;
}
#box {
  @media (min-width: 1200px) {
    .container {
      max-width: 1140px;
    }

    padding-left: 15px;
    padding-right: 60px;
  }
}
</style>
