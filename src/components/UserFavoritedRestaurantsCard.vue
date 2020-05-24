<template>
  <div class="card">
    <div class="card-header">
      <strong>{{ profile.FavoritedRestaurants.length }}}</strong> 收藏的餐廳
    </div>
    <div class="card-body" v-for="restaurant in profile.FavoritedRestaurants" :key="restaurant.id">
         <router-link :to="{ name: 'restaurant', params:{ id: restaurant.id} }">
          <img class="avatar" :src="restaurant.image" width="60" height="60" />
        </router-link>
    </div>
  </div>
</template>>

<script>
export default {
  props:{
    initialProfile: {
      type: Object,
      required: true
    },
  },
  data ( ) {
    return {
      profile: this.initialProfile,
    }
  }
}
</script>