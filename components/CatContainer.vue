<template>
  <div :class="$style.cat_container">
    <img :src="cat.url" :alt="cat.uuid" :class="$style.image" />

    <div :class="$style.info_container">
      <div><span :class="$style.label">撮影場所:</span> {{ cat.address }}</div>
      <div>
        <span :class="$style.label">撮影日:</span>
        {{ cat.createDate | moment }}
      </div>
    </div>
    <v-divider></v-divider>
  </div>
</template>

<script>
export default {
  props: {
    cat: {
      type: Object,
      default: null,
    },
  },
}
</script>

<style lang="scss" module>
.cat_container {
  padding-bottom: 16px;
  margin-bottom: 16px;

  .info_container {
    padding: 16px 0;
  }

  .image {
    max-width: 100%;
    max-height: 500px;
    object-fit: contain;
  }

  .label {
    font-weight: bold;
    width: 80px;
    display: inline-block;
  }
}
</style>
