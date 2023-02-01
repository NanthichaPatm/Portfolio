<script>
import feather from "feather-icons";

export default {
  props: ["projectInfo"],
  data() {
    return {
      tech:{},
    };
  },

  mounted() {
    feather.replace();
    console.log(this.projectInfo.technologies)
    this.tech = this.projectInfo.technologies;
    console.log(this.tech)
  },
  updated() {
    feather.replace();
  },
};
</script>

<template>
  <div class="block sm:flex gap-0 sm:gap-10 mt-14">
    <!-- Single project left section details -->
    <div class="w-full sm:w-1/3 text-left">
      <!-- Single project technologies -->
      <div class="mb-7">
        <p
          class="
            font-general-medium
            text-2xl text-ternary-dark
            dark:text-ternary-light
            mb-2
          "
        >
          {{ projectInfo.technologies.title }}
        </p>
        <p
          class="font-general-regular text-primary-dark dark:text-ternary-light"
        >
          {{ projectInfo.technologies.techs.join(", ") }}
        </p>
      </div>
    </div>

    <!-- Single project right section details -->
    <div class="w-full sm:w-2/3 text-left mt-10 sm:mt-0">
      <div class="mb-7">
        <p
          class="
            font-general-medium
            text-2xl text-ternary-dark
            dark:text-ternary-light
            mb-2
          "
        >
          {{ projectInfo.projectDetailsHeading }}
        </p>
        <p
          class="
            font-general-regular
            text-lg text-primary-dark
            dark:text-ternary-light
          "
        >
          {{ projectInfo.projectDetail }}
        </p>
      </div>
      <p
        class="
          font-general-regular
          mb-5
          text-lg text-ternary-dark
          dark:text-ternary-light
        "
      >
        {{ projectInfo.objectivesDetails }}
      </p>
      <div class="flex justify-center sm:block">
        <a
          :href="projectInfo.technologies.git"
          class="
            flex
            justify-center
            items-center
            w-36
            sm:w-48
            mt-12
            mb-6
            sm:mb-0
            text-lg
            border border-green-200
            dark:border-ternary-dark
            py-2.5
            sm:py-3
            shadow-lg
            rounded-lg
            bg-green-100
            focus:ring-1 focus:ring-green-800
            hover:bg-green-900
            text-gray-500
            hover:text-white
            duration-500
          "
          aria-label="goto Github"
        >
          <i
            data-feather="log-in"
            class="ml-0 sm:ml-1 mr-2 sm:mr-3 w-5 sm:w-6 duration-100"
          ></i>
          <span class="text-sm sm:text-lg font-general-medium duration-100"
            >Github</span
          ></a
        >
        <a v-if="tech.demo != undefined"
          :href="projectInfo.technologies.demo"
          class="
            flex
            justify-center
            items-center
            w-36
            sm:w-48
            mt-12
            mb-6
            sm:mb-0
            text-lg
            border border-gray-200
            dark:border-ternary-dark
            py-2.5
            sm:py-3
            shadow-lg
            rounded-lg
            bg-gray-100
            focus:ring-1 focus:ring-gray-800
            hover:bg-gray-900
            text-gray-500
            hover:text-white
            duration-500
          "
          aria-label="goto demo"
        >
        <i
            data-feather="eye"
            class="ml-0 sm:ml-1 mr-2 sm:mr-3 w-5 sm:w-6 duration-100"
          ></i>
          <span class="text-sm sm:text-lg font-general-medium duration-100"
            >Demo</span
          ></a
        >
        
      </div>
    </div>
  </div>
</template>
