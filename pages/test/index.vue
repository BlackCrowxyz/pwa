<template>
  <v-card>
    <v-card-title>Barcodes:{{ $route.query.barcode }}</v-card-title>
    <svg ref="bcs"></svg>
  </v-card>
</template>

<script>
import JsBarcode from "JsBarcode";

export default {
  data: () => {
    return {
      barcode: "",
    };
  },
  mounted() {
    JsBarcode(this.$refs["bcs"], this.$route.query.barcode);
  },
};
</script>

<style>
</style>