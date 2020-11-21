<template>
  <div class="plant_data">
    <router-view />
  </div>
</template>

<script>
export default {
  data() {
    return {
      tableData: [],
      formInline: {
        user: "",
        region: "",
      },
    };
  },
  methods: {
    onSubmit() {
      console.log("submit!");
    },
  },
};
</script>

<style>
</style>