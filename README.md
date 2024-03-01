## Vue Typing Text Component

The Vue Typing Text component is a flexible and customizable Vue.js component that simulates typing text effect. It allows you to display text as if it is being typed out character by character, with an optional blinking cursor at the end.

### Features:
- **Typing Effect:** Display text as if it is being typed out character by character.
- **Customizable Typing Speed:** Control the speed at which the text is typed out.
- **Customizable Text Styles:** Apply custom CSS classes to style the text.
- **Customizable Cursor:** Optionally display a blinking cursor at the end of the text.

### Usage:
```vue
<template>
  <VueTypingText
    :text="typedText"
    :typingSpeed="50"
    textClass="custom-text"
    cursorClass="custom-cursor"
  />
</template>

<script setup>
import VueTypingText from './VueTypingText.vue';

const typedText = 'Hello, world!';
</script>

<style>
.custom-text {
  color: blue;
  font-weight: bold;
}

.custom-cursor {
  color: red;
}
</style>
