<template>
  <div class="menu-book">
    <div class="book-cover">
      <h1> Daftar Menu Restoran</h1>
      <p>Silakan pilih menu favoritmu!</p>
    </div>

    <div class="menu-list">
      <RestaurantList @tampilkan-detail="lihatDetail" :aktif="terpilih?.nama" />
    </div>

    <transition name="fade">
      <RestaurantInfo v-if="terpilih" :nama="terpilih.nama">
        <template #deskripsi>
          <p>{{ terpilih.deskripsi }}</p>
        </template>
      </RestaurantInfo>
    </transition>
  </div>
</template>

<script>
import RestaurantList from './components/RestaurantList.vue';
import RestaurantInfo from './components/RestaurantInfo.vue';

export default {
  components: { RestaurantList, RestaurantInfo },
  data() {
    return {
      terpilih: null
    };
  },
  methods: {
    lihatDetail(data) {
      this.terpilih = data;
    }
  }
};
</script>

<style>
body {
  margin: 0;
  font-family: 'Georgia', serif;
  background: linear-gradient(to bottom right, #fef6e4, #fcd5ce);
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

.menu-book {
  background: #fffaf0;
  border: 2px solid #cba135;
  box-shadow: 0 0 20px rgba(0,0,0,0.1);
  border-radius: 16px;
  padding: 40px;
  max-width: 900px;
  width: 100%;
}

.book-cover {
  text-align: center;
  padding-bottom: 20px;
  border-bottom: 2px dashed #cba135;
  margin-bottom: 20px;
}

.book-cover h1 {
  font-size: 2.5rem;
  color: #7c3e2e;
}

.menu-list {
  margin-bottom: 20px;
}

.fade-enter-active, .fade-leave-active {
  transition: opacity 0.5s ease;
}
.fade-enter, .fade-leave-to {
  opacity: 0;
}
</style>