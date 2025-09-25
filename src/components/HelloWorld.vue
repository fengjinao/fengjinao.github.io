<template>
  <div class="hello-world-container">
    <SplitText text="Hello, GSAP!" class-name="text-2xl font-semibold text-center" :delay="100" :duration="0.6"
      ease="power3.out" split-type="chars" :from="{ opacity: 0, y: 40 }" :to="{ opacity: 1, y: 0 }" :threshold="0.1"
      root-margin="-100px" text-align="center" @animation-complete="handleAnimationComplete" />
    <CircularText text="VUE * BITS * IS AWESOME * " :spin-duration="20" on-hover="speedUp" class-name="text-blue-500"
      :curve-amount="100" />
    <!-- <CurvedLoop marquee-text="Be ✦ Creative ✦ With ✦ Vue ✦ Bits ✦" :speed="2" :curve-amount="400" direction="left"
      :interactive="true" /> -->
    <div class="ascii-container">
      <AsciiText text="YuBoWang" :ascii-font-size="8" :text-font-size="200" text-color="#fdf9f3" :plane-base-height="8"
        :enable-waves="true" class-name="w-full h-full" />
    </div>
    <div class="ascii-container" style="height: 600px;display: flex;justify-content: center;">
      <ProfileCard name="Javi A. Torres" title="Software Engineer" handle="javicodes" status="Online"
        contact-text="Contact Me" avatar-url="/assets/person.png" icon-url="/assets/iconpattern.png"
        grain-url="/assets/grain.webp" :show-user-info="true" :show-behind-gradient="false" :enable-tilt="true"
        @contact-click="handleContactClick" />
    </div>

  </div>
</template>

<script setup lang="ts">
import ProfileCard from "./ProfileCard.vue";
import SplitText from "./SplitText.vue";
import CircularText from "./CircularText.vue";
import CurvedLoop from "./CurvedLoop.vue";
import AsciiText from "./AsciiText.vue";

const handleAnimationComplete = () => {
  console.log('All letters have animated!');
};
const handleContactClick = () => {
  console.log('Contact button clicked!');
};
</script>

<style scoped>
.hello-world-container {
  position: relative;
  width: 100%;
  height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.ascii-container {
  background: #0b0b0b;
  border: 1px solid #333;
  position: relative;
  width: 100%;
  height: 400px;
  margin-top: 20px;
}

.ascii-text-container {
  height: 100%;
}
</style>