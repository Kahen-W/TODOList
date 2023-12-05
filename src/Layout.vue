<template>
  <nav>
    <ul class="flex gap-6">
      <li>
        <router-link to="/" class="btn btn-outline btn-accent">Home</router-link>
      </li>
      <li>
        <router-link to="/about" class="btn btn-outline btn-accent">About</router-link>
      </li>
      <li>
        <router-link to="/privacy" class="btn btn-outline btn-accent"
          >Privacy</router-link
        >
      </li>
    </ul>
  </nav>
  <main>
    <router-view></router-view>
  </main>
</template>
