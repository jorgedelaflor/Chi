<template lang="pug">
  div
    <TitleBar title="Search input" description="Search inputs are used for inputting words or phrases and locating relevant content." :tabs="pageTabs" />
    .chi-grid__container.-pt--3
      .chi-tabs-panel.-active#examples
        <Examples />
      .chi-tabs-panel#properties
        <Properties />
      .chi-tabs-panel#accessibility
        <Accessibility />
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import Examples from './examples/index.vue';
import PageContentTabs from '../../../../components/PageContentTabs.vue';
import Properties from './_properties.vue';
import Accessibility from './_accessibility.vue';
import { standardComponentPageTabs } from '../../../../constants/constants';

Vue.config.ignoredElements = ['chi-search-input', 'chi-brand'];

@Component({
  components: {
    Examples,
    Accessibility,
    PageContentTabs,
    Properties
  },
  data: () => {
    return {
      pageTabs: standardComponentPageTabs
    };
  }
})
export default class SearchInput extends Vue {}
</script>
