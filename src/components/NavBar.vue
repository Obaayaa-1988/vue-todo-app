<template>
  <header>
    <div>
      <nav>
        <ul class="text-center">
          <li class="inline-block pl-8 cursor-pointer">
            <router-link to="/">Home</router-link>
          </li>
          <li class="inline-block pl-8 cursor-pointer ">
            <router-link to="/">Blog</router-link>
          </li>
          <li class="inline-block pl-8 cursor-pointer ">
            <router-link to="about">About</router-link>
          </li>
        </ul>
      </nav>
    </div>
  </header>
</template>

<script>
export default {
  name: "NavBar",
};
</script>
