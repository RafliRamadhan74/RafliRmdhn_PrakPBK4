<template>
  <div class="info-card">
    <h2>{{ nama }}</h2>
    <slot name="deskripsi"></slot>
  </div>
</template>

<script>
export default {
  props: {
    nama: String
  }
};
</script>

<style scoped>
.info-card {
  margin-top: 30px;
  padding: 20px;
  border-radius: 12px;
  background: white;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
  max-width: 600px;
  margin-left: auto;
  margin-right: auto;
}
</style>
