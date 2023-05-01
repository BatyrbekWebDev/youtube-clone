<template>
  <div class="fixed bg-white w-full h-14 p-3 z-10 flex">
    <BaseToolTip @click="$emit('close')" text="Back" right>
      <button class="mr-2 p-2 focus:outline-none">
        <BaseIcon name="arrowLeft" class="w-5 h-5" />
      </button>
    </BaseToolTip>
    <TheSearch />
    <BaseToolTip text="Search with your voice">
      <button class="p-2 focus:outline-none">
        <BaseIcon name="microphone" class="w-5 h-5" />
      </button>
    </BaseToolTip>
  </div>
</template>

<script>
import BaseIcon from './BaseIcon.vue';
import BaseToolTip from './BaseToolTip.vue';
import TheSearch from './TheSearch.vue';

export default {
  components: {
    TheSearch,
    BaseToolTip,
    BaseIcon,
  },
  mounted() {
    window.addEventListener('click', this.onClick);
  },

  methods: {
    onClick(event) {
      if (!this.$el.contains(event.target)) {
        this.$emit('close');
      }
    },
  },
};
</script>
