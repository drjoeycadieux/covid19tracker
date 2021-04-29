<template>
  <div class="grid md:grid-cols-2 gap-4">
    <!-- Box 1 -->
    <div class="shadow-md bg-blue-100 p-10 text-center rounded">
      <h3 class="text-3xl text-blue-900 font-bold mb-4">Cases</h3>

      <div class="text-2xl mb-">
        <span class="font-bold">New:</span>
        {{ numberWithPoint(stats.NewDeaths) }}
      </div>

      <div class="text-2xl mb-">
        <span class="font-bold">Total:</span>
        {{ numberWithPoint(stats.TotalDeaths) }}
      </div>
    </div>
    <!-- Box 2 -->
    <div class="shadow-md bg-blue-200 p-10 text-center rounded">
      <h3 class="text-3xl text-blue-900 font-bold mb-4">Deaths</h3>

      <div class="text-2xl mb-">
        <span class="font-bold">New:</span>
        {{ numberWithPoint(stats.NewConfirmed) }}
      </div>

      <div class="text-2xl mb-">
        <span class="font-bold">Total:</span>
        {{ numberWithPoint(stats.TotalConfirmed) }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "DataBoxes",
  props: ["stats"],
  methods: {
    numberWithPoint(x) {
      return x.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ",");
    },
  },
};
</script>