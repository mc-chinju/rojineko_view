<template>
  <v-row dense>
    <template v-for="cat in cats">
      <v-col :key="cat.uuid" cols="12" lg="6" md="12">
        <cat-container :cat="cat" />
      </v-col>
    </template>
  </v-row>
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
        'https://livlog.xyz/webapi/cats.json'
      )
      this.cats = response.data.results
    } catch (err) {
      const res = err.response
      alert(res)
    }
  },
}
</script>
