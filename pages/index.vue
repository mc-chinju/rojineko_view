<template>
  <v-row></v-row>
</template>

<script>
export default {
  async created() {
    try {
      const response = await this.$axios.get(
        'https://jsondata.okiba.me/v1/json/7lV2J201227155106'
      )
      console.log(response)
    } catch (err) {
      const res = err.response
      console.log(res)
    }
  },
}
</script>
