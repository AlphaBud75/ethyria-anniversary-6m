<template>
  <div id="page-home" class="pb-4">
    <div class="header"></div>
    <div class="background"></div>
    <div class="section mb-4">
      <button id="show-modal" @click="showModal = true">Watch Intro Again</button>
      <SectionHero />
    </div>
    <div class="section mb-12">
      <modal class="modal" :show="showModal" @close="showModal = false">
        <modal />
      </modal>
      <SectionImage />
    </div>
    <div class="section mb-12">
      <SectionTimeline />
    </div>
    <div class="section mb-12">
      <SectionMessages />
    </div>
    <div class="section mb-12">
      <SectionCredits />
    </div>
  </div>
</template>

<script>
import SectionHero from "@/components/SectionHero.vue";
import SectionImage from "@/components/SectionImage.vue";
import SectionTimeline from "@/components/SectionTimeline.vue";
import SectionMessages from "@/components/SectionMessages.vue";
import SectionCredits from "@/components/SectionCredits.vue";

import modal from "@/components/ModalOpening.vue";

export default {
  data: () => ({
    showModal: true, //initial state
  }),
  name: "HomeView",
  components: {
    SectionHero,
    SectionImage,
    SectionTimeline,
    SectionMessages,
    SectionCredits,

    modal,
  },
};
</script>

<style lang="scss" scoped>
#show-modal {
  color: black;
  opacity: 0.5;
  
}

.modal {
  z-index: 99;
}

#page-home {
  // background-color: #d0d4ec;
  min-height: 100vh;
  padding: 1px;
}
.header {
  width: 100vw;
  height: 797px;
  // 858ED1
  background-image: url("../assets/img/header.png");
  background-position: top center;
  background-repeat: no-repeat;
  position: absolute;
  top: -60px;
  left: 0;
  right: 0;
  z-index: 2;
}
.background {
  width: 100vw;
  height: 100vh;
  // 858ED1
  background-color: #d0d4ec;
  background-image: url("../assets/img/header.png");
  background-size: cover;
  background-position: center center;
  filter: blur(10px);
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: 1;
  opacity: 0.5;
}
.section {
  position: relative;
  z-index: 3;
  .section-grid {
    min-height: 400px;
    &.section-box {
      background-color: rgba(255, 255, 255, 0.8);
      border-color: #858ed1;
      border-right: 4px solid #858ed1;
      border-bottom: 4px solid #858ed1;
    }
  }
}
</style>

<style lang="scss">
.white-glow {
  text-shadow: 0px 0px 3px #fff, 0px 0px 3px #fff, 1px 1px 2px #fff;
}
</style>
