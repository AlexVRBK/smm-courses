<template>
  <header
    class="flex top-0 sticky z-50 py-7 justify-between bg-bodyColor mx-5 xs:mx-14 lg:!mx-auto lg:max-w-5xl"
  >
    <Logo />

    <nav class="justify-between self-center">
      <button
        @click="menuOpen = !menuOpen"
        class="md:hidden float-right cursor-pointer hover:opacity-60"
      >
        <Icon
          :icon="menuOpen ? 'ep:close-bold' : 'ep:menu'"
          class="text-3xl text-titleColor"
          aria-label="menu mobile"
        />
      </button>

      <div :class="menuOpen ? 'flex' : 'hidden'" class="md:flex">
        <ul
          class="flex flex-col absolute md:!relative right-0 2xs:right-5 top-24 py-5 rounded-lg bg-containerColor text-titleColor text-center font-semibold md:flex-row md:top-0 md:!right-0 md:space-x-8 lg:space-x-10 md:py-0 md:bg-transparent"
        >
          <NavLink text="SMM" link="#product" />

          <NavLink text="Куратори" link="#mentor" />

          <NavLink text="Реєстрація" link="#register" />
        </ul>
      </div>
    </nav>
  </header>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import Logo from '../atoms/Logo.vue'
import NavLink from '../atoms/NavLink.vue'
import { Icon } from '@iconify/vue'

export default defineComponent({
  components: {
    Logo,
    NavLink,
    Icon
  },
  data() {
    return {
      menuOpen: false
    }
  }
})
</script>
