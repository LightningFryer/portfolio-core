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
  <div class="flex w-screen h-screen justify-center items-center">
    <div class="flex flex-col gap-y-7 w-[60%] justify-center items-center">
      <h1
        class="landing-text text-4xl font-ibm font-thin text-white text-center"
      >
        there is no need for a good portfolio when you have websites to show for
        it
      </h1>
      <div class="flex flex-row gap-x-10">
        <a
          target="_blank"
          href="https://www.clubgraphica.tech/"
          class="website-link text-3xl opacity-0 translate-y-[100%] hover:text-4xl font-ibm font-thin hover:font-semibold transition-[font] hover:underline duration-300 text-white"
          >clubgraphica.tech</a
        >
        <a
          target="_blank"
          href="https://electrovista-core-rework.vercel.app/"
          class="website-link text-3xl opacity-0 translate-y-[100%] hover:text-4xl font-ibm font-thin hover:font-semibold transition-[font] hover:underline duration-300 text-white"
          >electrovista.tech</a
        >
      </div>
    </div>
  </div>
</template>
