<template>
  <div class="card">
    <div class="card-header">
      <strong>{{ profile.Followings.length }}</strong> followings (追蹤者)
    </div>
    <div class="card-body row" v-for="following in profile.Followings" :key="following.id">
        <router-link :to="{ name: 'users-profile', params:{ id: following.id} }">
          <img class="avatar" :src="following.image" width="60" height="60" />
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