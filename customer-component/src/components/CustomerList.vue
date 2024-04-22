<template>
  <div>
    <h2>Customer List</h2>
    <input
      type="text"
      v-model="newCustomer"
      placeholder="Enter customer name"
      @keyup.enter="addCustomer"
    />
    <button @click="addCustomer">Add Customer</button>
    <select v-if="customers.length > 0">
      <option disabled value="">Select a customer</option>
      <option v-for="customer in customers" :key="customer">{{ customer }}</option>
    </select>
    <p v-else>No customers added yet.</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newCustomer: '',
      customers: []
    };
  },
  methods: {
    addCustomer() {
      if (this.newCustomer.trim() !== '') {
        this.customers.push(this.newCustomer.trim());
        this.newCustomer = ''; // Clear input after adding customer
      }
    }
  }
};
</script>

<style>
/* Add styles as needed */
</style>
