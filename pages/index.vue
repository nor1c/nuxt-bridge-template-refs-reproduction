<template>
  <div>
    <Tutorial ref="tutorialRef" />
    <button @click="fireTutorial()">Click me!</button>
  </div>
</template>

<script setup>
const tutorialRef = ref(null)
const fireTutorial = () => {
  // this will return Nuxt Context in Nuxt Bridge
  console.log(tutorialRef.value)

  // this is how you normally call a function inside child component using Template Refs (not working in Nuxt Bridge)
  tutorialRef.value.fire()

  // function fire() is inside Nuxt Context -> _setupState (works in Nuxt Bridge)
  tutorialRef.value._setupState.fire()
}
</script>
