<template>
  <div class="flex justify-center items-center mt-52">
    <div class="w-full max-w-xs">
     <ValidationObserver v-slot="{ handleSubmit }" ref="loginForm">
                    <form @submit.prevent="handleSubmit(login)" class="bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4">
          <ValidationProvider name="Email" rules="required|email" v-slot="{ errors }">
            <div class="email-input mb-4">
              <label
                for="email"
                class="block text-gray-700 text-sm font-bold mb-2"
              >
                Email</label
              >
              <input
                id="email"
                class="shadow appearance-none borderrounded w-full py-2 px-3 text-gray-700 mb-3 leading-tight focus:outline-none focus:shadow-outline"
                type="text"
                placeholder="Email"
                aria-describedby="emailHelp"
                v-model="email"
              />

              <span class="text-xs text-red-700" id="emailHelp">{{
                errors[0]
              }}</span>
            </div>
          </ValidationProvider>

          <ValidationProvider
            name="Password"
            rules="required|min:6"
            v-slot="{ errors }"
          >
            <div class="password-input mb-6">
              <label
                for="password"
                class="block text-gray-700 text-sm font-bold mb-2"
                >Password</label
              >

              <input
                aria-describedby="passwordHelp"
                v-model="password"
                class="shadow appearance-none borderrounded w-full py-2 px-3 text-gray-700 mb-3 leading-tight focus:outline-none focus:shadow-outline"
                id="password"
                type="password"
                placeholder="*******"
              />

              <span class="text-xs text-red-700" id="emailHelp">{{
                errors[0]
              }}</span>
              <span class="text-xs text-red-700" id="passwordHelp"></span>
            </div>
          </ValidationProvider>
          <div class="flex items-center justify-between">
            <button
              class="bg-blue-600 hover:bg-black text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline"
              type="submit"
            >
              Sign In
            </button>
            <a
              class="inline-block align-baseline font-bold text-sm text-blue-500 hover:text-blue-800"
              href="#"
            >
              Forgot Password?
            </a>
          </div>
        </form>
      </ValidationObserver>
    </div>
  </div>
</template>

<script>
export default {
  name: "Login",
  data() {
    return {
      email: "",
      password: "",
    };
  },
  methods: {
    login() {
      console.log("logging in");
    },
  },
};
</script>
