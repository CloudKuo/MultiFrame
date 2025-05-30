<template>
  <div class="about">
    <div id="app">
      <div v-for="[key, api] in Object.entries(apiList)" :key="key">
        <label> Key: {{ key }} </label>
        <label> Value: {{ api.tt }} </label>
      </div>
      <button @click="addApiItem">Add New Item</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      apiList: {
        R: {
          tt: "t",
        },
        T: {
          tt: "t",
        },
      },
    };
  },
  methods: {
    addApiItem() {
      // Generate a new key dynamically (you can modify this logic)
      const newKey = "X"; 
      // Add a new object to the map
      this.$set(this.apiList, newKey, { tt: "new value" });

      // Alternatively, if using Vue 3:
      // this.apiList[newKey] = { tt: "new value" };
    },
  },
};
</script>
