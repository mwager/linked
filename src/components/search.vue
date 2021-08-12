<template>
  <div class="flex flex-col">
    <input
      type="search"
      :placeholder="$t('search')"
      class="h-16 rounded text-black"
      v-model="searchString"
    />

    {{ getContent }}

    <div v-for="result in results" :key="result.id">
      {{ result }}
    </div>
  </div>
</template>

<script>
import { mapGetters } from 'vuex'
import { Getters as FileGetters } from '@/store/modules/file/types'

export default {
  components: {},
  data() {
    return {
      searchString: ''
    }
  },
  computed: {
    ...mapGetters('file', [FileGetters.GET_CONTENT])
  },
  mounted() {}
}
</script>
