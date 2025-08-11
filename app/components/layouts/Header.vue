<script setup>
import { Ellipsis, X } from 'lucide-vue-next'

const showMenu = ref(false)
</script>

<template>
  <section class="pb-6">
    <nav class="container relative z-50 h-24 select-none">
      <div
        class="container relative flex flex-wrap items-center justify-end h-24 px-0 mx-auto overflow-hidden font-medium border-b border-gray-200 md:overflow-visible"
      >
        <div
          class="top-0 left-0 items-start w-full h-full p-4 text-sm bg-gray-900 bg-opacity-50 md:items-center md:w-full md:absolute lg:text-base md:bg-transparent md:p-0 md:relative md:flex"
          :class="{ 'flex fixed': showMenu, 'hidden': !showMenu }"
          @touchmove.prevent
        >
          <div
            class="flex-col w-full h-auto overflow-hidden rounded-lg bg-background md:overflow-visible md:rounded-none md:relative md:flex md:flex-row"
          >
            <div
              class="flex flex-col items-end justify-end w-full pt-4 md:items-center md:flex-row md:py-0 md:justify-end gap-2 md:gap-6 text-right"
            >
              <a
                class="px-6 py-2 text-gray-700 cursor-pointer dark:text-gray-300 md:px-3 md:py-2"
                href="/dashboard"
                title="Dashboard"
              >{{ $t('dashboard.title') }}</a>

              <SwitchLanguage />
              <SwitchTheme />
            </div>
          </div>
        </div>

        <div
          class="absolute right-0 flex flex-col items-center justify-center w-10 h-10 rounded-full cursor-pointer md:hidden hover:bg-muted"
          :class="{ 'right-2': showMenu }"
          @click="showMenu = !showMenu"
        >
          <Ellipsis v-show="!showMenu" class="w-6 h-6" />
          <X v-show="showMenu" class="w-6 h-6" />
        </div>
      </div>
    </nav>
  </section>
</template>
