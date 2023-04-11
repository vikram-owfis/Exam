<template>
  <div class="calendar bg-white rounded-lg shadow-md p-4 max-w-md mx-auto">
    <h1 class="text-2xl font-bold mb-4 text-center">Calendar</h1>
    <div class="calendar-header flex justify-between items-center mb-4">
      <button
        @click="previousMonth"
        class="text-gray-600 px-2 py-1 border border-gray-300 rounded-md focus:outline-none ml-2 bg-green-300 hover:bg-yellow-400"
      >
        &lt;
      </button>

      <div class="calendar-selectors flex items-center">
        <select
          v-model="selectedMonth"
          @change="updateCalendar"
          class="mr-2 p-3 border border-gray-300 rounded-md focus:outline-none text-gray-800 bg-purple-200 hover:bg-purple-300 px-7"
        >
          <option v-for="(month, index) in months" :value="index" :key="month">
            {{ month }}
          </option>
        </select>
        <select
          v-model="selectedYear"
          @change="updateCalendar"
          class="p-2 border border-gray-300 rounded-md focus:outline-none text-gray-800 bg-blue-200 hover:bg-blue-300 px-11 py-2"
        >
          <option v-for="year in years" :value="year" :key="year">
            {{ year }}
          </option>
        </select>
      </div>
      <button
        @click="nextMonth"
        class="text-gray-600 px-3 py-2 border border-gray-300 rounded-md focus:outline-none mr-2 bg-green-300 hover:bg-yellow-400"
      >
        &gt;
      </button>
    </div>

    <div class="calendar-grid grid grid-cols-7 gap-2">
      <div
        v-for="day in daysInMonth"
        :key="day"
        class="calendar-day text-gray-800 text-center flex justify-center items-center h-10 w-10 rounded-full bg-green-200 hover:bg-green-300"
      >
        {{ day }}
      </div>
    </div>
  </div>
</template>


<script setup lang="ts">
import {
  format,
  addMonths,
  subMonths,
  startOfMonth,
  endOfMonth,
  eachDayOfInterval,
} from "date-fns";
import { ref } from "vue";

const currentDate = new Date();
const years = ref<number[]>([]);
const months = ref<string[]>([]);
const selectedYear = ref<number | null>(null);
const selectedMonth = ref<number | null>(null);

const currentMonth = format(currentDate, "MMMM yyyy");
const daysInMonth = eachDayOfInterval({
  start: startOfMonth(currentDate),
  end: endOfMonth(currentDate),
}).map((date) => format(date, "dd"));

const nextMonth = () => {
  currentDate.value = addMonths(currentDate.value, 1);
  updateSelectedYearMonth();
};

const previousMonth = () => {
  currentDate.value = subMonths(currentDate.value, 1);
  updateSelectedYearMonth();
};

const initializeYearsAndMonths = () => {
  const currentYear = new Date().getFullYear();
  for (let year = currentYear - 10; year <= currentYear + 10; year++) {
    years.value.push(year);
  }

  months.value.push(
    "January",
    "February",
    "March",
    "April",
    "May",
    "June",
    "July",
    "August",
    "September",
    "October",
    "November",
    "December"
  );

  selectedYear.value = currentYear;
  selectedMonth.value = new Date().getMonth();
};

const updateCalendar = () => {
  const updatedDate = new Date(selectedYear.value!, selectedMonth.value!);
  currentDate.value = updatedDate;
};

const updateSelectedYearMonth = () => {
  selectedYear.value = currentDate.value.getFullYear();
  selectedMonth.value = currentDate.value.getMonth();
};

initializeYearsAndMonths();
</script>

