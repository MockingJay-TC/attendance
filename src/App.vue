<script setup></script>
<template >
  <header
    class="h-[80px] flex items-center justify-between max-w-full px-8 md:px-16 font-[Poppins] border-b z-20 bg-[#f0f5f5]"
  >
    <div class="md:text-4xl text-2xl font-bold text-[#54c278]">TheAttend</div>
    <nav class="flex items-center md:gap-x-8 gap-x-2 text-[#54c278]">
      <RouterLink to="/">ListerPage</RouterLink>
    </nav>
  </header>
  <RouterView />
</template>
