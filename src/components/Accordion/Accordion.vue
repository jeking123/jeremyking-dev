<template>
  <div class="custom-accordion w-100 pt-2">
    <div class="accordion-item pb-3">
      <div class="accordion-header" @click="toggleAccordion(0)">
        <span>{{ props.title }}</span>
        <v-icon icon="mdi-chevron-down" />
      </div>
      <transition name="accordion-slide">
        <div v-show="activeAccordion === 0" class="accordion-content">
          <p>
            {{ props.description }}
          </p>
        </div>
      </transition>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const props = defineProps({
  title: String,
  description: String,
});

const activeAccordion = ref(null);

const toggleAccordion = (index) => {
  if (activeAccordion.value === index) {
    activeAccordion.value = null;
  } else {
    activeAccordion.value = index;
  }
};
</script>

<style lang="scss">
.custom-accordion {
  .accordion-item {
    overflow: hidden;
  }

  .accordion-header {
    display: flex;
    justify-content: space-between;
    align-items: center;

    cursor: pointer;
    transition: background-color 0.3s ease;
  }

  // Vue transition classes for accordion slide animation
  .accordion-slide-enter-active,
  .accordion-slide-leave-active {
    transition: all 1s ease;
    transform-origin: top;
    overflow: hidden;
  }

  .accordion-slide-enter-from {
    opacity: 0;
    transform: scaleY(0);
    max-height: 0;
  }

  .accordion-slide-enter-to {
    opacity: 1;
    transform: scaleY(1);
    max-height: 200px;
  }

  .accordion-slide-leave-from {
    opacity: 1;
    transform: scaleY(1);
    max-height: 200px;
  }

  .accordion-slide-leave-to {
    opacity: 0;
    transform: scaleY(0);
    max-height: 0;
  }
}
</style>
