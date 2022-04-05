<template>
<transition name=fade>
  <div v-if="num == 0" class="main-img">
    <img src="@/assets/img/1alt.png" alt="" />
  </div>
  <div v-else-if="num == 1" class="main-img">
    <img src="@/assets/img/2.png" alt="" />
  </div>
  <div v-else-if="num == 2" class="main-img">
    <img src="@/assets/img/3.png" alt="" />
  </div>
  <div v-else-if="num == 3" class="main-img">
    <img src="@/assets/img/4.png" alt="" />
  </div>
  <div v-else-if="num == 4" class="main-img">
    <img src="@/assets/img/5.png" alt="" />
  </div>
</transition>
</template>

<script>
export default {
  name: "MainImg",
  props: ["num"],
  data() {
    return {};
  },
  methods: {},
  setup() {},
};
</script>

<style lang="scss" scoped>
.main-img img {
    width: 40vw;
    height: auto;
}

.fade-enter-active{
  transition: opacity .7s ease;
}
.fade-leave-active {
  transition: opacity 0s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

@media (max-width: 768px) {
.main-img img {
    width: 80vw;
    height: auto;
}
}

@media (max-width: 570px) {
.main-img img {
    width: 100vw;
    height: auto;
}
}

</style>