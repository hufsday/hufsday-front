<template>
  <div class="rounded border border-gray-200 overflow-hidden">
    <div class="bg-navy text-white p-2.5">
      <svg
        class="w-5 h-5 float-left"
        fill="none"
        stroke="currentColor"
        viewBox="0 0 24 24"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M4 6h16M4 12h16M4 18h16"
        ></path>
      </svg>
      <div class="ml-6 text-sm">메뉴</div>
    </div>

    <div class="p-2 bg-sky">
      <div class="text-navy font-medium text-sm">COMMUNITY</div>
    </div>

    <div v-for="menu in splitedCommunityMenus" :key="menu">
      <NuxtLink :to="menu.link">
        <div class="p-1.5 bg-white border-b border-gray-200 hover:bg-gray-50">
          <svg
            class="w-4 h-4 text-navy float-left mt-0.5"
            fill="none"
            stroke="currentColor"
            viewBox="0 0 24 24"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M9 5l7 7-7 7"
            ></path>
          </svg>
          <div class="text-sm">{{ menu.title }}</div>
        </div>
      </NuxtLink>
    </div>

    <div class="p-2 bg-sky">
      <div class="text-navy font-medium text-sm">LIFE</div>
    </div>

    <div
      v-for="menu in splitedLifeMenus"
      :key="menu"
      class="p-1.5 bg-white border-b border-gray-200 hover:bg-gray-50"
    >
      <svg
        class="w-4 h-4 text-navy float-left mt-0.5"
        fill="none"
        stroke="currentColor"
        viewBox="0 0 24 24"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M9 5l7 7-7 7"
        ></path>
      </svg>
      <div class="text-sm">{{ menu.title }}</div>
    </div>

    <div class="p-2 bg-sky">
      <div class="text-navy font-medium text-sm">
        STUDY
      </div>
    </div>

    <div
      v-for="menu in splitedStudyMenus"
      :key="menu"
      class="p-1.5 bg-white border-b border-gray-200 hover:bg-gray-50"
    >
      <svg
        class="w-4 h-4 text-navy float-left mt-0.5"
        fill="none"
        stroke="currentColor"
        viewBox="0 0 24 24"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M9 5l7 7-7 7"
        ></path>
      </svg>
      <div class="text-sm">{{ menu.title }}</div>
    </div>

    <div class="p-2 bg-sky">
      <div class="text-navy font-medium text-sm">
        HOBBY
      </div>
    </div>

    <div
      v-for="(menu, index) in splitedHobbyMenus"
      :key="menu"
      :class="[
        'p-1.5 bg-white hover:bg-gray-50',
        index === 4 ? null : 'border-b border-gray-200',
      ]"
    >
      <svg
        class="w-4 h-4 text-navy float-left mt-0.5"
        fill="none"
        stroke="currentColor"
        viewBox="0 0 24 24"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M9 5l7 7-7 7"
        ></path>
      </svg>
      <div class="text-sm">{{ menu.title }}</div>
    </div>
  </div>
</template>

<script>
import MenuItem from './MenuItem.json'

export default {
  data() {
    return {
      menus: MenuItem,
    }
  },
  computed: {
    splitedCommunityMenus() {
      return this.menus.slice(0, 7)
    },
    splitedLifeMenus() {
      return this.menus.slice(7, 12)
    },
    splitedStudyMenus() {
      return this.menus.slice(12, 18)
    },
    splitedHobbyMenus() {
      return this.menus.slice(18, 23)
    },
  },
}
</script>
