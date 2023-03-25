<template >
    <div class=" bg-slate-200 container mx-auto p-4">
      <form class="bg-slate-200 rounded-lg shadow-md p-8">
        <h2 class="text-2xl font-bold mb-4">Ambulance Booking Form</h2>
        <!-- <div class="mb-4">
          <label class="block text-gray-700 font-bold mb-2" for="name">
            Name
          </label>
          <input
            class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
            id="name"
            type="text"
            placeholder="Enter your name"
          />
        </div> -->
        <!-- <div class="mb-4">
          <label class="block text-gray-700 font-bold mb-2" for="email">
            Email
          </label>
          <input
            class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
            id="email"
            type="email"
            placeholder="Enter your email address"
          />
        </div> -->
        <div class="mb-4">
          <label class="block text-gray-700 font-bold mb-2" for="date">
            Date
          </label>
          <input
            class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
            id="date"
            type="date"
          />
        </div>
        <div class="mb-4">
          <label class="block text-gray-700 font-bold mb-2" for="time">
            Time
          </label>
          <input
            class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
            id="time"
            type="time"
          />
        </div>
      </form>

      <!--   <div class="mb-4">
          <label class="block text-gray-700 font-bold mb-2" for="service">
            Service
          </label>
          <select
            class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
            id="service"
          >
            <option value="">Choose a service</option>
            <option value="Haircut">Haircut</option>
            <option value="Coloring">Coloring</option>
            <option value="Styling">Styling</option>
          </select>
        </div> -->
        <div class="mb-14">
          <label class="block text-gray-700 font-bold mb-2" for="stylist">
       Available ambulance
          </label>
          <select
            class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
            id="stylist"
          >
            <option value="">Choose a ambulance</option>
            <option value="John">option 1</option>
            <option value="Jane">option 2</option>
            <option value="Sarah">option 2</option>
          </select>
        </div>
        <div class="flex items-center justify-center">
          <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded focus:outline-none focus">
          submit</button>
            </div>
        </div>
    
             
        </template>
        <script>
            export default {
                
            }
            </script>
           
           <style>
           
           </style> 
  