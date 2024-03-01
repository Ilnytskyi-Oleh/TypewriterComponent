<template>
  <div :class="[textClass, 'typed', {'cursor': showCursor}]">
    <span>{{ typedText }}</span>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';

const props = defineProps({
  text: {
    type: String,
    required: true,
    validator: (value) => typeof value === 'string'
  },
  typingSpeed: {
    type: Number,
    default: 50
  },
  textClass: {
    type: String,
    default: ''
  },
});

const typedText = ref('');
const textLength = ref(0);
const showCursor = ref(true);

const type = () => {
  if (textLength.value <= props.text.length) {
    typedText.value = props.text.slice(0, textLength.value++);
    setTimeout(type, props.typingSpeed);
  } else {
    setTimeout(() => {
      showCursor.value = false;
    }, 2000)
  }
};

onMounted(type);
</script>

<style scoped>
.typed {
  font-family: "Courier New", "Lucida Console", monospace;
  vertical-align: text-bottom;
}


.cursor:after {
  content: "|";
  animation: blink .9s step-end infinite;
}

@keyframes blink {
  from, to { color: transparent }
  50% { color: inherit }
}
</style>