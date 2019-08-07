<template>
  <div>
    <b-container>
      <b-row>
        <b-col cols="12" md="4">
          <b-card
            title="BTC"
            img-src="https://i.ibb.co/0XxT0VH/BTC.png"
            img-alt="BTC"
            img-top
            tag="article"
            style="max-width: 19rem;"
            
          >
            <b-card-text><strong>Ultima transaccion:</strong>{{btc.time}} <br><strong>Tarifa: </strong>{{btc.rate}}  </b-card-text>
          </b-card>
        </b-col>

        <b-col cols="12" md="4">
          <b-card
            title="XRP"
            img-src="https://i.ibb.co/gm6W0dG/XRP.png"
            img-alt="Image"
            img-top
            tag="article"
            style="max-width: 19rem;"
            
          >
            <b-card-text><strong>Ultima transaccion:</strong>{{xrp.time}} <br><strong>Tarifa: </strong>{{btc.rate}} </b-card-text>
          </b-card>
        </b-col>

        <b-col cols="12" md="4">
          <b-card
            title="ETH"
            img-src="https://i.ibb.co/Z1Ktm4x/ETH.png"
            img-alt="Image"
            img-top
            tag="article"
            style="max-width: 19rem;"
            
          >
            <b-card-text><strong>Ultima transaccion:</strong> {{eth.time}} <br><strong>Tarifa:</strong>{{btc.rate}} </b-card-text>
          </b-card>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>
<script>
export default {
  name: "Bitcoincard",
  props: {
    btc: {
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
      },
    xrp: {
        time: String,
        asset_id_base: String,
        asset_id_quote: String,
        rate: Number
      }
  }
};
</script>

<style lang="sass" scoped>
div
    margin-top: 20px
img
  margin: 0 auto
  width: 50%
</style>

