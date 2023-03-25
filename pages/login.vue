<template>
    <div class="flex  bg-slate-200 items-center justify-center h-screen">
      <div class="w-full max-w-sm">
        <h2 class="text-3xl font-bold text-gray-900 text-center mb-6">  Login</h2>
        <form @submit.prevent="submitForm" class="bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4">
          <div class="mb-4">
            <label class="block text-gray-700 font-bold mb-2" for="email">
              Email
            </label>
            <input
              class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
              id="email"
              type="email"
              v-model="email"
              required
              placeholder="Enter your email address"
            />
          </div>
          <div class="mb-4">
            <label class="block text-gray-700 font-bold mb-2" for="password">
              Password
            </label>
            <input
              class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
              id="password"
              type="password"
              v-model="password"
              required
              placeholder="Enter your password"
            />
          </div>
          <div class="flex items-center justify-between">
            <button
              class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline"
              type="submit"
            >
              Sign In
            </button>
          </div>
        </form>
      </div>
    </div>
  </template>
  
  <script>
  import {createClient} from "@supabase/supabase-js"
  const supabaseUrl = 'https://mohfultvbzlkahggbnxx.supabase.co'
  const supabaseKey = 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6Im1vaGZ1bHR2Ynpsa2FoZ2dibnh4Iiwicm9sZSI6ImFub24iLCJpYXQiOjE2Njg1MTYyMTcsImV4cCI6MTk4NDA5MjIxN30.KCNzdXJHbheJy4UODDMoC0J5-aAqLMkShGanSz396aY '

  const supabase = createClient(supabaseUrl,supabaseKey)
  
  export default {
     
    data() {
      return { 
        email:"", 
        password:"",  
        
      };
    },
    methods: {
       // Handle form submission logic here
     async submitForm() { 
     
        const {data, error} = await supabase
        .from("users")
        .insert({
            
            email:this.email,
            
            password:this.password,
             
           
        })

        if(error){
            console.log("Shit ain't working",error.message)

        }
        else{
            alert("tyou are now logged successfully",data)
            this.$router.push('/user')
        }
      },
    },
  };
  </script>
  
  