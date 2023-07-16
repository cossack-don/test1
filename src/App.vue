<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
import styled from 'vue3-styled-components'

interface Test {
  sx?: string | { toString: () => string } | undefined
  da?: boolean
}
const sx = {
  sx: {},
  da: Boolean
}
//s
const SberPaper = styled('div', sx)`
  padding: 15px;
  background: ${(props) => (props.da ? 'yellow' : 'red')};
  ${(props: Test) => props.sx};
`

const x = () => {
  fetch('https://petstore.swagger.io/v2/pet/25')
    .then((res) => res.json())
    .then((res) => console.log(res))
}
x()
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

  <SberPaper :sx="{ color: 'blue' }" da>Test</SberPaper>
  <RouterView />
</template>
