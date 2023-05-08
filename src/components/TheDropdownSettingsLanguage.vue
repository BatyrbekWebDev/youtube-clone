<template>
  <DropdownSettingsHeader title="Choose your language" @back="$emit('select-menu', 'main')" />
  <section class="py-2">
    <ul class="max-h-96 overflow-auto">
      <DropdownSettingsListItem 
        v-for="(languageName, languageId) in languages" 
        :key="languageId" 
        :label="languageName"
        :active="languageId === selectedOptions.languageId" 
        @click="selectOption(languageId)" />
    </ul>
  </section>
</template>

<script>
import DropdownSettingsListItem from './DropdownSettingsListItem.vue';
import DropdownSettingsHeader from './DropdownSettingsHeader.vue'

export default {
  components: {
    DropdownSettingsListItem,
    DropdownSettingsHeader
  },
  props: ['selectedOptions'],
  emits: ['select-menu', 'select-option'],
  data() {
    return {
      selectedLanguageId: 0,
      languages: ['English', 'Russia',],
    };
  },
  methods: {
    selectOption(languageId) {
      this.$emit('select-option', {name: 'languageId', value: languageId})
    }
  }
};
</script>
