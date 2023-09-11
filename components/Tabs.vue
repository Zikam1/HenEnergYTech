<template>
  <div
    class="border border-gray-100 px-5 py-4 xs:px-6 lg:px-10 lg:py-5 capitalize font-bold text-gray-400 cursor-pointer border-b-2 border-transparent; text-xs lg:text-base grid place-items-center text-center"
  >
    <ul class="container overflow-x-auto scroll pb-0">
      <li
        v-for="(tab, index) in tabs"
        :key="index"
        class=""
        :class="{ active: isTabActive(tab) }"
        @click="tabClicked(tab)"
      >
        <span v-if="typeof tab === 'object' && 'text' in tab">{{
          tab.text
        }}</span>
        <span v-else>{{ tab }}</span>
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import Vue, { PropType } from "vue";

type TabObject = {
  text: string;
  value: string;
};

type Tab = string | TabObject;

export default {
  props: {
    tabs: {
      type: Array as PropType<Tab[]>,
    },
    routify: {
      type: Boolean,
      default: false,
    },
    selected: {
      type: String,
    },
  },
  methods: {
    tabClicked(tab: Tab) {
      this.$emit("change", tab);
      const activeTab =
        typeof tab === "object" && "value" in (tab as TabObject)
          ? (tab as TabObject).value
          : tab;

      if (this.routify) {
        this.$router.push({
          path: this.$route.name!,
          query: {
            "active-tab": activeTab as string,
          },
        });
      }
    },
    isTabActive(tab: Tab): boolean {
      if (
        typeof tab === "object" &&
        "value" in tab &&
        (tab as TabObject).value === this.selected
      ) {
        return true;
      }

      if (tab === this.selected) {
        return true;
      }

      return false;
    },
  },
  mounted() {
    if (this.routify) {
      const activeTab = this.$route.query["active-tab"] as string;

      if (activeTab) {
        // important to emit the tab from the tabs prop because the spelling may differ in letter casing
        // between the tabs and the "active-tab" query
        const tab = this.tabs.find((tab) => {
          if (typeof tab === "string") {
            return (tab as string).toLowerCase() === activeTab.toLowerCase();
          }

          return (
            (tab as TabObject).value.toLowerCase() === activeTab.toLowerCase()
          );
        });
        if (tab) this.tabClicked(tab);
      }
    }
  },
};
</script>

<style scoped>
/* .tabs-wrapper {
  @apply border-b border-gray-100;
}

ul {
  @apply pb-0;
} */

/* .header-item {
  @apply px-5 py-4 xs:px-6 lg:px-10 lg:py-5 capitalize font-bold text-gray-400 cursor-pointer;
  @apply border-b-2 border-transparent;
  @apply text-xs lg:text-base;
  @apply grid place-items-center text-center;
} */

/* .header-item.active {
  @apply text-ccl-red-800;
  @apply border-b-2 border-ccl-red-800;
} */

/* Hide scrollbar for Chrome, Safari and Opera */
.scroll::-webkit-scrollbar {
  display: none;
}

/* Hide scrollbar for IE, Edge and Firefox */
.scroll {
  -ms-overflow-style: none; /* IE and Edge */
  scrollbar-width: none; /* Firefox */
}
</style>
