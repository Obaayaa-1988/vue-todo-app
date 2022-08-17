<template>
  <div>
    <header class="flex justify-evenly pb-20 pt-12">
      <div>
        <nav>
          <ul class="text-center">
            <li class="inline-block pl-8 cursor-pointer text-2xl text-white font-mono font-semibold
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
                font-semibold
              "
            >
              <router-link to="/">Blog</router-link>
            </li>
            <li
              class="
                inline-block
                pl-8
                cursor-pointer
                text-2xl text-white
                font-mono
                font-semibold
              "
            >
              <router-link to="about">About</router-link>
            </li>
          </ul>
        </nav>
      </div>

      <div>
        <button  class="bg-white text-black py-3 px-8 rounded font-mono">Log In</button>
        <button class="bg-pink-500 text-white py-3 px-8 rounded ml-4 font-mono " >Sign Up</button>
      </div>
    </header>
  </div>
</template>

<script>
export default {
  name: "NavBar",
};
</script>
