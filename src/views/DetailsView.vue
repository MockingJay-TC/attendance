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
    class="md:h-screen overflow-hidden relative flex items-center justify-between max-w-full px-8 md:px-16 font-[Poppins] border-b z-20 bg-[#f0f5f5]"
  >
    <div
      class="relative w-full md:w-[62%] h-full md:h-[700px] border-4 md:border-r-[#54c278] mx-auto py-12 px-4 shadow-lg rounded-lg bg-[#64371f]"
    >
      <div
        class="md:absolute relative w-52 md:mt-0 mx-auto md:w-96 md:h-full object-fill md:-top-10 md:-left-32"
      >
        <img
          class="rounded-lg shadow-lg"
          src="../assets/profile2.jpg"
          alt="Profile"
        />
      </div>
      <div class="md:ml-72 ml-2 relative mt-4 md:mt-0">
        <div
          class="md:absolute md:-left-32 top-0 md:text-8xl text-2xl font-[Satisfy] text-white flex items-center"
        >
          <!-- Name -->
          <div>
            {{ student.name }}
          </div>
          <!-- age -->
          <div
            class="md:ml-16 ml-4 md:text-xl text-sm rounded-[50%] w-[35px] h-[35px] md:w-[60px] md:h-[60px] md:leading-[60px] leading-[35px] text-center shadow-xl bg-white text-[#64371f]"
          >
            {{ student.age }}yrs
          </div>
        </div>
        <!-- email -->
        <div class="md:pt-28 pt-4 text-[white] font-light">
          {{ student.email }}
        </div>
        <!-- special -->
        <div class="md:mt-8 mt-2 text-white md:text-xl text-md">
          <div>{{ student.special }} Developer</div>
        </div>
        <!-- Skills -->
        <div class="text-white md:mt-8 mt-2 md:text-2xl text-lg">
          <div class="text-[#c8c8c1] tracking-wide font-semibold">Skills</div>
          <div class="flex gap-5 text-sm">
            <ul v-for="skill in student.skills" :key="skill">
              <li
                class="tracking-wide md:text-md text-sm list-disc ml-6 uppercase"
              >
                {{ skill }}
              </li>
            </ul>
          </div>
        </div>
        <!-- About -->
        <div class="md:pt-14 pt-4 text-white">
          <div
            class="md:text-2xl text-lg font-semibold tracking-wide text-[#c8c8c1]"
          >
            About
          </div>
          <div class="max-w-xl md:text-justify text-left text-sm md:text-md">
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
