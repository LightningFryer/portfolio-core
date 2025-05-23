<script setup>
import gsap from "gsap";
import { SplitText } from "gsap/SplitText";
gsap.registerPlugin(SplitText);

onMounted(() => {
  const landingText = new SplitText(".landing-text");

  gsap
    .from(landingText.words, {
      opacity: 0,
      scale: 1.5,
      stagger: 0.15,
    })
    .then(() => {
      gsap.to(".website-link", {
        duration: 0.5,
        opacity: 1,
        yPercent: -100,
      });
    });
});
</script>

<template>
  <div class="landing-sec flex w-screen h-screen justify-center items-center">
    <div
      class="flex flex-col gap-y-16 w-[60%] justify-center items-center mt-10"
    >
      <!-- <h1
        class="landing-text text-4xl font-ibm font-thin text-white text-center"
      >
        there is no need for a good portfolio when you have websites to show for
        it
      </h1> -->
      <div class="flex flex-row gap-x-4 justify-center items-center">
        <a
          class="text-3xl hover:text-4xl font-ibm font-thin hover:font-semibold transition-[font] hover:underline duration-300 text-white"
          >whoami?</a
        >
        <p class="text-white text-4xl font-ibm font-thin">|</p>
        <a
          class="text-3xl hover:text-4xl font-ibm font-thin hover:font-semibold transition-[font] hover:underline duration-300 text-white"
          >github</a
        >
        <p class="text-white text-4xl font-ibm font-thin">|</p>
        <a
          class="text-3xl hover:text-4xl font-ibm font-thin hover:font-semibold transition-[font] hover:underline duration-300 text-white"
          >linkedin</a
        >
      </div>
      <div class="flex flex-col justify-center items-center gap-y-3">
        <div>
          <p class="text-white font-ibm font-thin text-3xl">my websites</p>
        </div>
        <div class="flex flex-row gap-x-10">
          <a
            target="_blank"
            href="https://www.clubgraphica.tech/"
            class="website-link text-2xl opacity-0 translate-y-[100%] hover:text-4xl font-ibm font-thin hover:font-semibold transition-[font] hover:underline duration-300 text-white"
            >clubgraphica.tech</a
          >
          <a
            target="_blank"
            href="https://electrovista-core-rework.vercel.app/"
            class="website-link text-2xl opacity-0 translate-y-[100%] hover:text-4xl font-ibm font-thin hover:font-semibold transition-[font] hover:underline duration-300 text-white"
            >electrovista.tech</a
          >
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.landing-sec {
  background-color: transparent;
  background: radial-gradient(circle, #444444 8%, transparent 1%) 0 0 / 20px
    20px;
  background-size: 35px 35px; /* !!!!!THIS SHOULD BE SAME AS THE BACKGROUND POSITION CELL SIZE IN THE KEYFRAME OTHERWISE YOU'LL SEE HORRIBLE STUTTERING!!!!! */
  animation: moveLeft 2s linear infinite;
}

@keyframes moveLeft {
  0% {
    background-position: 0 0;
  }
  100% {
    background-position: 35px -35px; /* Moves by exactly one grid cell size */
  }
}
</style>
