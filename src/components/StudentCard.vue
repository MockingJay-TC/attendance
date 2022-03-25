<script>
import DetailsView from "../views/DetailsView.vue";
export default {
  props: ["students", "search"],
  components: {
    DetailsView,
  },
  data() {
    return {
      checkedNames: [],
    };
  },
  created() {
    console.log(this.filteredStudents);
  },

  methods: {
    onClickMe(e, student) {
      if (e.target.checked) {
        this.checkedNames.push(student.name);
      } else {
        this.checkedNames = this.checkedNames.filter(
          (name) => name != student.name
        );
      }
      this.$emit("studentList", this.checkedNames);
    },
    sendDetials(student) {
      this.$router.push({ name: "details", params: student });
    },
  },
  computed: {
    filteredStudents() {
      return JSON.parse(
        JSON.stringify(
          this.students.filter((student) =>
            student.name.toLowerCase().includes(this.search.toLowerCase())
          )
        )
      );
    },
  },
};
</script>
<template>
  <div
    v-for="student in filteredStudents"
    :key="student.id"
    class="w-80 relative shadow-lg p-8 rounded-lg border-t-4 border-[#54c278] bg-gradient-to-b from-[#ffffff] to-[#fefefe]"
  >
    <input
      class="w-6 h-6 absolute right-8 appearance-none border-2 rounded-md checked:bg-[#54c278]"
      type="checkbox"
      :id="student.id"
      :value="student.name"
      @click="(e) => onClickMe(e, student)"
    />
    <img
      class="h-28 w-28 object-cover rounded-[50%] shadow-md mx-auto my-6"
      src="../assets/profile1.jpg"
      alt="Profile"
    />
    <h3 class="text-center my-2 text-xl text-semibold tracking-wider">
      {{ student.name }}
    </h3>
    <h5 class="text-[#a8a6a6] text-center">{{ student.email }}</h5>
    <div class="flex items-center gap-5 justify-between">
      <div class="p-3 shadow-md rounded-lg my-3">
        <div class="text-[grey] text-sm">Specialization</div>
        <div class="flex items-center gap-3 my-1 text-[#c49042]">
          <div class="w-3 h-3 rounded-[50%] bg-[#c49042]"></div>
          <div>{{ student.special }}</div>
        </div>
      </div>
      <div
        class="text-center shadow-sm hover:shadow-md py-3 px-5 rounded-xl hover:tracking-wider cursor-pointer bg-[#54c278] text-[white] hover:text-[#f0f5f5] hover:bg-[#878a8a] transition duration-500"
        @click="sendDetials(student)"
      >
        View
      </div>
    </div>
  </div>
</template>
