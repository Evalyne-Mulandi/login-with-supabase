<template>
    <div class="flex flex-col bg-slate-300  items-center justify-center h-screen">
      <h1 class="text-3xl font-bold mb-4">Ambulance Status Table</h1>
      <table class="table-auto  bg-slate-100 w-full">
        <thead>
          <tr>
            <th class="px-4 py-2">Ambulance No.</th>
            <th class="px-4 py-2">Status</th>
            <th class="px-4 py-2">Driver Name</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(driver, index) in drivers" :key="driver.id">
            <td class="border  border-spacing-1 px-4 py-2">{{ index + 1 }}</td>
            <td class="border px-4 py-2">{{ driver.status }}</td>
            <td class="border px-4 py-2">{{ driver.name }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        drivers: [
          { id: 1, status: 'Available', name: 'John Smith' },
          { id: 2, status: 'Unavailable', name: 'Jane Doe' },
          { id: 3, status: 'On Duty', name: 'Bob Johnson' },
          { id: 4, status: 'On Duty', name: 'Bob Johnson' },
          { id: 5, status: 'On Duty', name: 'Bob Johnson' },
          { id: 6, status: 'On Duty', name: 'Bob Johnson' },
          { id: 7, status: 'On Duty', name: 'Bob Johnson' },
        ],
      };
    },
  };
  </script>
  
  <style>
  /* Optional: add custom styles here */
  </style>
  