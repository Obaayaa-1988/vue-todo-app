<template>
  <div>
    <header class="flex justify-evenly pb-20 pt-12 py-2.5">
      <div>
        <nav class="">
          <ul class="text-center sm:text-center">
            <li
              class="
                inline-block
                pl-8
                cursor-pointer
                text-2xl text-white
                font-mono
                
              "
            >
              <router-link to="/">Home</router-link>
            </li>
            <li
              class="
                inline-block
                pl-8
                cursor-pointer
                text-2xl text-white
                font-mono
              "
            >
              <router-link to="/blog">Blog</router-link>
            </li>
            <li
              class="
                inline-block
                pl-8
                cursor-pointer
                text-2xl text-white
                font-mono
              "
            >
              <router-link to="/about">About</router-link>
            </li>
          </ul>
        </nav>
      </div>

      <div>
        <button class="bg-white text-black py-3 px-8 rounded font-mono md:px-6">
          Log In
        </button>
        <button
          class="bg-red-400 text-white py-3 px-8 rounded ml-4 font-mono md:px-6"
        >
          Sign Up
        </button>
      </div>
    </header>
  </div>
</template>

<script>
export default {
  name: "NavBar",
};
</script>
