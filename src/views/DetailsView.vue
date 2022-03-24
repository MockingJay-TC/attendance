<script>
export default {
  data() {
    return {
      student: null,
    };
  },
  methods: {
    sendBack() {
      this.$router.push("/");
      console.log("clicked");
    },
  },
  created() {
    this.student = this.$route.params;
  },
};
</script>
<template>
  <div
    class="h-screen overflow-hidden relative flex items-center justify-between max-w-full px-8 md:px-16 font-[Poppins] border-b z-20 bg-[#f0f5f5]"
  >
    <div
      class="relative w-full md:w-[62%] h-full md:h-[700px] border-4 md:border-r-[#54c278] mx-auto py-12 px-4 shadow-lg rounded-lg bg-[#64371f]"
    >
      <div
        class="md:absolute relative md:w-96 md:h-full object-fill md:-top-10 md:-left-32"
      >
        <img
          class="rounded-lg shadow-lg"
          src="../assets/profile2.jpg"
          alt="Profile"
        />
      </div>
      <div class="ml-72 relative">
        <div
          class="absolute -left-32 top-0 text-8xl font-[Satisfy] text-white flex items-center"
        >
          <!-- Name -->
          <div>
            {{ student.name }}
          </div>
          <!-- age -->
          <div
            class="ml-16 text-xl rounded-[50%] w-[60px] h-[60px] leading-[60px] text-center shadow-xl bg-white text-[#64371f]"
          >
            {{ student.age }}yrs
          </div>
        </div>
        <!-- email -->
        <div class="pt-28 text-[white] font-light">
          {{ student.email }}
        </div>
        <!-- special -->
        <div class="mt-8 text-white text-xl">
          <div>{{ student.special }} Developer</div>
        </div>
        <!-- Skills -->
        <div class="text-white mt-8 text-2xl">
          <div class="text-[#c8c8c1] tracking-wide font-semibold">Skills</div>
          <div class="flex gap-5 text-sm">
            <ul v-for="skill in student.skills" :key="skill">
              <li class="tracking-wide text-md list-disc ml-6 uppercase">
                {{ skill }}
              </li>
            </ul>
          </div>
        </div>
        <!-- About -->
        <div class="pt-14 text-white">
          <div class="text-2xl font-semibold tracking-wide text-[#c8c8c1]">
            About
          </div>
          <div class="max-w-xl text-justify">
            {{ student.about }}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Bubblegum+Sans&family=Dancing+Script:wght@400;500;600;700&family=Satisfy&display=swap");
</style>
