<template>
  <div class="mt-4 rounded overflow-hidden border border-gray-200">
    <div class="p-2 bg-gray-300">
      <div class="text-gray-600 font-medium text-sm">LINKS</div>
    </div>

    <div v-for="(menu, index) in menus" :key="menu">
      <a :href="menu.link" target="_blank">
        <div
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
      </a>
    </div>
  </div>
</template>

<script>
import QuickLinkItem from './QuickLinkItem.json'

export default {
  data() {
    return {
      menus: QuickLinkItem,
    }
  },
}
</script>
