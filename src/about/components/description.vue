
<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue';

// Your existing code here
const dateStartedCoding = new Date(2022, 9, 5);

const timeDifference = ref({
  hours: 0,
  minutes: 0,
  seconds: 0,
});

const updateElapsedTime = () => {
  const currentDate = new Date();
  const timeDifferenceInMilliseconds = currentDate.getTime() - dateStartedCoding.getTime();
  timeDifference.value = {
    hours: Math.floor(timeDifferenceInMilliseconds / (1000 * 60 * 60)),
    minutes: Math.floor((timeDifferenceInMilliseconds % (1000 * 60 * 60)) / (1000 * 60)),
    seconds: Math.floor((timeDifferenceInMilliseconds % (1000 * 60)) / 1000),
  };
};

// Update the elapsed time every second (1000 milliseconds)
let timerId: number;

onMounted(() => {
  updateElapsedTime(); // Update immediately when the component is mounted
  timerId = setInterval(updateElapsedTime, 1000);
});

onUnmounted(() => {
  clearInterval(timerId); // Clear the interval when the component is unmounted to avoid memory leaks
});
</script>
<template>
    <div class="text-xs text-black border-black rounded-sm border-opacity-5 bg-opacity-5">
      <p>It has been 
        <em class="pl-1 pr-1 text-white bg-black bg-opacity-75 rounded-sm w-44">{{ timeDifference.hours }} Hours {{ timeDifference.minutes }} Minutes {{ timeDifference.seconds }} Seconds</em>
        into my coding journey. I initially got into programming seeking to automate and enhance my trading strategies. But web development caught my eye, the fusion of logic and creativity aligned with my visual tendencies. And now, here I am :).
      </p>

      <p>
      </p>



    </div>
</template>
