<template>
    <div class="flex  bg-slate-200 items-center justify-center h-screen">
      <div class="w-full max-w-sm">
        <h2 class="text-3xl font-bold text-gray-900 text-center mb-6"> Sign in</h2>
        <form @submit.prevent="submitForm" class="bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4">
            <div class="mb-4">
            <label class="block text-gray-700 font-bold mb-2" for="name">
              Name
            </label>
            <input
              class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
              id="name"
              type="name"
              v-model="name"
              required
              placeholder="Enter your name"
            />
          </div>
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
            <label class="block text-gray-700 font-bold mb-2" for="contact">
              Contact
            </label>
            <input
              class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
              id=" contact"
              type=" contact"
              v-model="contact"
              required
              placeholder="Enter your contact"
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
           <!-- <div class="mb-4">
            <label class="block text-gray-700 font-bold mb-2" for="confirm password">
             Confirm Password
            </label>
            <input
              class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
              id=" confirm-password"
              type="confirm-password"
              v-model=" confirm_password"
              required
              placeholder="Enter your confirm password"
            />
          </div>  -->
          <div class="flex items-center justify-center">
            <button
              class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline"
              type="submit"> 
              Sign In
            </button>

          </div>
          <div class="flex  justify-center items-center text-sm text-black">
          <span class="text-sm text-black">Made with ❤️ by Mulash</span>
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
        name:"",
        email:"",
        contact:"",
        password:"",
        
        
        
      };
    },
    methods: {
       // Handle form submission logic here
     async submitForm() { 
      // if (this.email.length < 1) {
      //   this.err = "Email is required";
      //   return;
      // }
      // if (this.password.length < 8) {
      //   this.err = "Password must be at least 8 characters";
      //   return;
      // }
      
      // /* get user from supabase and check if email exists */
      // const main_user = await supabase.auth.getUser();
      // /* check if email of the texists  */
      // if (!this.email.includes("@")) {
      //   this.err = "Email is invalid";
      //   return;
      // }
        const {data, error} = await supabase
        .from("users")
        .insert({
            name:this.name,
            email:this.email,
            contact:this.contact,
            password:this.password,
             
           
        })

        if(error){
            console.log("Shit ain't working",error.message)

        }
        else{
            alert("account created successfully",data)
            this.$router.push('/login')
        }
      },
    },
  };
  </script>
  