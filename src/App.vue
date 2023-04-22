<template>
  <TheHeader @toggle-sidebar="toggleSidebar" />

  <TheSidebarSmall :is-open="isCompactSidebarOpen" />

  <TheSidebar :is-open="isSidebarOpen" />

  <TheSidebarMobile
    :is-open="isMobileSidebarOpen"
    @close="closeMobileSidebar"
  />

  <TheCategories :is-sidebar-open="isSidebarOpen" />

  <TheVideos :is-sidebar-open="isSidebarOpen" />
</template>

<script>
import TheHeader from './components/TheHeader.vue';
import TheSidebarSmall from './components/TheSidebarSmall.vue';
import TheSidebar from './components/TheSidebar.vue';
import TheSidebarMobile from './components/TheSidebarMobile.vue';
import TheCategories from './components/TheCategories.vue';
import TheVideos from './components/TheVideos.vue';

export default {
  components: {
    TheHeader,
    TheSidebarSmall,
    TheSidebar,
    TheSidebarMobile,
    TheCategories,
    TheVideos,
  },
  data() {
    return {
      sidebarState: null,
      isCompactSidebarOpen: false,
      isSidebarOpen: false,
      isMobileSidebarOpen: false,
    };
  },
  mounted() {
    if (window.innerWidth >= 768 && window.innerWidth < 1280) {
      this.sidebarState = 'compact';
    }
    if (window.innerWidth >= 1280) {
      this.sidebarState = 'normal';
    }
    this.onResize();
    window.addEventListener('resize', this.onResize);
  },
  methods: {
    onResize() {
      if (window.innerWidth < 768) {
        this.isCompactSidebarOpen = false;
        this.isSidebarOpen = false;
      } else if (window.innerWidth < 1280) {
        this.isCompactSidebarOpen = true;
        this.isSidebarOpen = false;
      } else {
        this.isCompactSidebarOpen = this.sidebarState === 'compact';
        this.isSidebarOpen = this.sidebarState === 'normal';
      }
    },
    toggleSidebar() {
      if (window.innerWidth >= 1280) {
        this.sidebarState =
          this.sidebarState === 'normal' ? 'compact' : 'normal';
        this.onResize();
      } else {
        this.openMobileSidebar();
      }
    },
    openMobileSidebar() {
      this.isMobileSidebarOpen = true;
    },
    closeMobileSidebar() {
      this.isMobileSidebarOpen = false;
    },
  },
};
</script>
