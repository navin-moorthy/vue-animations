<template>
  <div class="home">
    <section>
      <button @click="bounce = !bounce">Bounce</button>
      <br />
      <transition name="bounce">
        <img v-if="bounce" alt="Vue logo" src="../assets/logo.png" />
      </transition>
    </section>
    <section>
      <button @click="roll = !roll">Roll</button>
      <br />
      <transition name="roll">
        <img v-if="roll" alt="Vue logo" src="../assets/logo.png" />
      </transition>
    </section>
    <section>
      <button @click="animated = !animated">Animated</button>
      <br />
      <transition
        name="animated"
        enter-active-class="animated flipInY"
        leave-active-class="animated zoomOutRight"
      >
        <img v-if="animated" alt="Vue logo" src="../assets/logo.png" />
      </transition>
    </section>
  </div>
</template>

<script>
export default {
  name: "home",
  data() {
    return { bounce: false, roll: false, animated: false };
  }
};
</script>

<style>
section {
  max-height: 250px;
}

.bounce-enter-active {
  animation: bounce-in 0.5s;
}

.bounce-leave-active {
  animation: bounce-in 0.5s reverse;
}

@keyframes bounce-in {
  0% {
    transform: scale(0);
  }

  50% {
    transform: scale(1.5);
  }

  100% {
    transform: scale(1);
  }
}

.roll-enter-active {
  animation: roll-in 0.5s;
}

.roll-leave-active {
  animation: roll-in 0.5s reverse;
}

@keyframes roll-in {
  0% {
    transform: scale(0) rotate(0deg) translateX(-250px);
    opacity: 0;
  }

  100% {
    transform: scale(1) rotate(360deg) translateX(0px);
    opacity: 1;
  }
}
</style>
