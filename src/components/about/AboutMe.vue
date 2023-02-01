<script>
export default {
	setup() {
		return {
			bios: [
				{
					id: 1,
					bio:
						'Experienced Engineer turned Front-End Developer with a passion for design. Proficient in HTML, CSS, and JavaScript. Strong problem-solving skills, ability to deliver visually appealing and functional user interfaces, and expertise in Agile methodologies. Looking to apply my technical skills and engineering background to a new challenge in Front-End Development.',
				},
				{
					id: 2,
					bio:
						"Having a passion for front-end web development is a great first step towards a rewarding career in this field. As a beginner, it's natural to feel overwhelmed with the amount of information and skills required. However, with dedication and hard work, anyone can learn and master the necessary skills to become a successful front-end developer.",
				},
			],
		};
	},
};
</script>

<template>
  <div class="block sm:flex sm:gap-10 mt-10 sm:mt-20">
    <!-- About profile image -->
    <div class="w-full sm:w-1/4 mb-7 sm:mb-0">
      <img src="@/assets/images/me.jpg" class="rounded-xl w-96" alt="" />
    </div>

    <!-- About details -->
    <div class="w-full sm:w-3/4 text-left">
      <p
        v-for="bio in bios"
        :key="bio.id"
        class="
          font-general-regular
          mb-4
          text-ternary-dark
          dark:text-ternary-light
          text-lg
        "
      >
        {{ bio.bio }}
      </p>
    </div>
  </div>
</template>
