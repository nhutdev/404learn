<template>
   <!-- https://play.tailwindcss.com/MIwj5Sp9pw -->
<div class="py-16">
    <div class="flex bg-white rounded-lg shadow-lg overflow-hidden mx-auto max-w-sm lg:max-w-4xl">
        <div class="hidden lg:block lg:w-1/2 bg-cover"
            style="background-image:url('https://images.unsplash.com/photo-1546514714-df0ccc50d7bf?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=667&q=80')">
        </div>
        <div class="w-full p-8 lg:w-1/2">
            <h2 class="text-2xl font-semibold text-gray-700 text-center">404Learn</h2>
            <p class="text-xl text-gray-600 text-center">Welcome back!</p>
           
            <div class="mt-4 flex items-center justify-between">
                <span class="border-b w-1/5 lg:w-1/4"></span>
                <a href="#" class="text-xs text-center text-gray-500 uppercase">Đăng nhập bằng tài khoản</a>
                <span class="border-b w-1/5 lg:w-1/4"></span>
            </div>
            <div class="mt-4">
                <label class="block text-gray-700 text-sm font-bold mb-2">Tài khoản</label>
                <input v-model="username" class="bg-gray-200 text-gray-700 focus:outline-none focus:shadow-outline border border-gray-300 rounded py-2 px-4 block w-full appearance-none" type="text" />
            </div>
            <div class="mt-4">
                <div class="flex justify-between">
                    <label class="block text-gray-700 text-sm font-bold mb-2">Mật khẩu</label>
                   
                </div>
                <input v-model="password" class="bg-gray-200 text-gray-700 focus:outline-none focus:shadow-outline border border-gray-300 rounded py-2 px-4 block w-full appearance-none" type="password" />
            </div>
            <div class="mt-8">
                <button class="bg-gray-700 text-white font-bold py-2 px-4 w-full rounded hover:bg-gray-600" @click="login">Đăng nhập</button>
            </div>
        </div>
    </div>
</div>
</template>
 
  <script>
  export default {
    data() {
      return {
        imgs: ["/src/assets/img_4k/1.jpg"],
        users: [
        { username: "luan", password: "luan123" },
        { username: "nhut", password: "nhut123" },
        { username: "thanh", password: "thanh123" },
      ],
      username:'',password:''
      };
    },
    components: {},
    mounted() {},
    methods: {
    login() {
      const matchedUser = this.users.find(user =>
        user.username === this.username && user.password === this.password
      );
      
      if (matchedUser) {
        localStorage.setItem('user', JSON.stringify(matchedUser));
        this.$router.push({ path: '/home' })
      } else {   
        alert('Tên đăng nhập hoặc mật khẩu không đúng');
      }
    }},
  };
  </script>