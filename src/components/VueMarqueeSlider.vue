<script setup>
import { ref, computed, onMounted, useCssModule } from "vue";
const props = defineProps({
  autoWidth: {
    type: Boolean,
    default: () => {
      return false;
    },
  },
  height: {
    type: Number,
    default: () => {
      return 200;
    }
  },
  id: {
    type: String,
    required: true,
    default: () => {
      return "id";
    },
  },
  paused: {
    type: Boolean,
    default: () => {
      return false;
    },
  },
  repeat: {
    type: Number,
    default: () => {
      return 10;
    },
  },
  reverse: {
    type: Boolean,
    default: () => {
      return false;
    },
  },
  space: {
    type: Number,
    default: () => {
      return 200;
    },
  },
  speed: {
    type: Number,
    default: () => {
      return 1500;
    },
  },
  vertical: {
    type: Boolean,
    default: () => {
      return false;
    }
  },
  width: {
    type: Number,
    default: () => {
      return 100;
    },
  },
});

var container = ref(null);
var containerWidth = ref(0);
var items = ref([]);
var itemsLength = ref(0);
var itemsWidth = ref([]);
var style = ref(null);

const styleElement = computed(
  () =>
    `
      animation-duration: ${props.speed}ms;
      animation-direction: ${props.reverse ? "reverse" : "normal"};
      animation-play-state: ${props.paused ? "paused" : "running"};
      height: ${props.vertical ? props.height : 'auto'}
    `
);

onMounted(() => {
  style = useCssModule();
  setContainer();
  setItems();
  setItemsLength();
  calculateContainerWidth();
  setContainerWidth();
  cloneItems();
});

function calculateContainerWidth() {
  for (let index = 0; index < itemsLength; index++) {
    itemsWidth.value.push(items[index].offsetWidth);
    setItemSpace(index);

    if (props.autoWidth) {
      // if we are not using width specified by the user, we are setting the object-fit:contain for the images
      setImageObjectFit(index);
    } else {
      // if the user use the width property and want all items to be equal, the component will set the minWidth of the items
      setItemWidth(index);
    }
  }
  containerWidth = itemsWidth.value.reduce((a, b) => a + b, 0);
}

function cloneItems() {
  const repeatCounter = getRepeatCounter();
  for (let index = 0; index < repeatCounter; index++) {
    container.appendChild(items[index].cloneNode(true));
  }
}

function getRepeatCounter() {
  return items.length * props.repeat;
}

function setItems() {
  // get all childrens that will be put inside the slot of the component
  items = container.children;
}

function setItemsLength() {
  itemsLength = items.length;
}

function setItemSpace(index) {
  props.vertical ? items[index].style.marginBottom = `${props.space}px` : items[index].style.marginRight = `${props.space}px`;
}

function setItemWidth(index) {
  items[index].style.minWidth = `${props.width}px`;
}

function setImageObjectFit(index) {
  items[index].style.objectFit = "contain";
}

function setContainer() {
  container = document.querySelector(
    `#${props.id} .${props.vertical ? style.marqueeSliderContainerVertical : style.marqueeSliderContainer}`
  );
}

function setContainerWidth() {
  if (props.vertical) {
    container.style.width = 'auto';
  } else {
    if (props.autoWidth) {
      container.style.width = `${
        itemsLength * (containerWidth / itemsLength + props.space)
      }px`;
    } else {
      container.style.width = `${itemsLength * (props.width + props.space)}px`;
    }
  }
}
</script>

<template>
  <div :id="id" :class="$style.marqueeSlider">
    <div :class="vertical ? $style.marqueeSliderContainerVertical : $style.marqueeSliderContainer" :style="styleElement">
      <slot>
        <div>Hello</div>
        <div>From</div>
        <div>MarqueeSlider</div>
      </slot>
    </div>
  </div>
</template>

<style lang="css" module>
.marqueeSlider {
  overflow: hidden;
}

.marqueeSliderContainer {
  width: 100%;
  animation-name: horizontalAnimation;
  animation-timing-function: linear;
  animation-iteration-count: infinite;
  display: flex;
}

.marqueeSliderContainerVertical {
  height: fit-content;
  animation-name: verticalAnimation;
  animation-timing-function: linear;
  animation-iteration-count: infinite;
  display: flex;
  flex-direction: column;
}

@keyframes horizontalAnimation {
  0% {
    transform: translateX(0%);
  }
  100% {
    transform: translateX(-100%);
  }
}

@keyframes verticalAnimation {
  0% {
    transform: translateY(0%);
  }
  100% {
    transform: translateY(-100%);
  }
}
</style>
