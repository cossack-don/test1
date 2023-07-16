<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
import styled from 'vue3-styled-components'

interface Test {
  sx?: Object
  da?: boolean
}
const sx = {
  sx: {},
  da: Boolean
}
const SberPaper = styled('div', sx)`
  padding: 15px;
  background: ${(props) => (props.da ? 'yellow' : 'red')};
  ${(props: string) => props.sx};
`
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />

      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
      </nav>
    </div>
  </header>

  <SberPaper :sx="{ color: 'black' }" da>Test</SberPaper>
  <RouterView />
</template>
