<template>
  <div class="card">
    <div class="card-header">
      <strong>{{ profile.Followers.length }}</strong> followers (追隨者)
    </div>
    <div class="card-body" v-for="follower in profile.Followers" :key="follower.id">
      <router-link :to="{ name: 'users-profile', params:{ id: follower.id} }">
        <img :src="follower.image" width="60" height="60" class="avatar" />
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