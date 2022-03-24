<script>
import students from "../data/students.js";
import StudentCard from "../components/StudentCard.vue";
export default {
  name: "Home",
  components: {
    StudentCard,
  },
  emits: ["studentList"],
  data() {
    return {
      lister: [],
      students: students,
    };
  },
  methods: {
    getList(list) {
      this.lister = JSON.parse(JSON.stringify(list));
    },
  },
};
</script>

<template>
  <div class="border-[green] max-w-full px-8 md:px-16 bg-[#f0f5f5] h-full">
    <div
      class="flex items-center justify-center md:justify-between flex-wrap py-4"
    >
      <div class="text-3xl md:my-8 my-3 font-semibold">Attendance</div>
      <div>
        <input
          class="border py-2 px-3 rounded-md w-[250px] outline-none text-[grey] shadow-sm"
          placeholder="Search..."
        />
      </div>
    </div>
    <div class="my-1 text-2xl">
      Students In Class:
      <div class="text-xl my-2 flex gap-1 flex-wrap">
        <ul v-for="stud in lister" :key="stud">
          <li class="tracking-wide text-md list-disc ml-6 uppercase">
            {{ stud }}
          </li>
        </ul>
      </div>
    </div>
    <div class="flex flex-wrap gap-5 justify-between">
      <StudentCard :students="students" @studentList="getList" />
    </div>
  </div>
</template>
