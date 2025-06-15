<template>
  <div class="menu-buttons">
    <button
      v-for="resto in daftarRestoran"
      :key="resto.nama"
      @click="$emit('tampilkan-detail', resto)"
      :class="{ aktif: aktif === resto.nama }"
    >
      {{ resto.nama }}
    </button>
  </div>
</template>

<script>
export default {
  props: ['aktif'],
  data() {
    return {
      daftarRestoran: [
        {
          nama: 'Sate Ayam Pak Kumis',
          deskripsi: 'Sate ayam legendaris dengan bumbu kacang khas.'
        },
        {
          nama: 'Bakso Malang Jaya',
          deskripsi: 'Bakso Malang dengan kuah gurih dan bakso urat kenyal.'
        },
        {
          nama: 'Nasi Goreng Spesial',
          deskripsi: 'Nasi goreng spesial dengan topping telur dan ayam suwir.'
        },
        {
          nama: 'Mie Ayam Pangsit Mantap',
          deskripsi: 'Mie ayam dengan pangsit renyah dan saus spesial.'
        },
        {
          nama: 'Ayam Bakar Taliwang',
          deskripsi: 'Ayam bakar khas Lombok dengan rasa pedas manis.'
        },
        {
          nama: 'Ikan Bakar Jimbaran',
          deskripsi: 'Ikan bakar segar dengan sambal matah ala Bali.'
        },
        {
          nama: 'Rendang Padang Asli',
          deskripsi: 'Rendang daging sapi empuk dengan bumbu Padang otentik.'
        }
      ]
    };
  }
};
</script>

<style scoped>
.menu-buttons {
  display: flex;
  flex-wrap: wrap;
  gap: 12px;
  justify-content: center;
}
button {
  background-color: #fff;
  border: 2px solid #d4a373;
  border-radius: 12px;
  padding: 10px 16px;
  cursor: pointer;
  font-weight: bold;
  transition: all 0.3s ease;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);
}
button:hover {
  background-color: #ffe5b4;
}
.aktif {
  background-color: #d4a373;
  color: white;
  border-color: #b57f50;
}
</style>
