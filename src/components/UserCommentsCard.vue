<template>
  <div class="card">
    <div class="card-header">
      <strong>{{ profile.Comments.length }}</strong> 已評論餐廳
    </div>
    <div class="card-body" v-for="comment in profile.Comments" :key="comment.id">
         <router-link :to="{ name: 'restaurant', params:{ id: comment.Restaurant.id} }">
          <img class="avatar" :src="comment.Restaurant.image" width="60" height="60" />
        </router-link>
    </div>
  </div>
</template>

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