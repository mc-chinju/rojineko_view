<template>
  <div>
    <template v-for="cat in cats">
      <cat-container :key="cat.uuid" :cat="cat" />
    </template>
  </div>
</template>

<script>
import CatContainer from '@/components/CatContainer.vue'

export default {
  components: {
    CatContainer,
  },
  data() {
    return {
      cats: [],
    }
  },
  async created() {
    try {
      const response = await this.$axios.get(
        'https://jsondata.okiba.me/v1/json/7lV2J201227155106'
      )
      this.cats = response.data.results
    } catch (err) {
      const res = err.response
      alert(res)
    }
  },
}
</script>
