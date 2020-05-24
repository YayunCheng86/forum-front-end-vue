<template>
  <div class="card mb-3">
    <div class="row no-gutters">
      <div class="col-md-4">
        <img :src="profile.image" width="300px" height="300px" />
      </div>
      <div class="col-md-8">
        <div class="card-body">
          <h5 class="card-title">{{ profile.name }}</h5>
          <p class="card-text">{{ profile.email }}</p>
          <ul class="list-unstyled list-inline">
            <li>
              <strong>{{ profile.Comments.length }}</strong> 已評論餐廳
            </li>
            <li>
              <strong>{{ profile.FavoritedRestaurants.length }}</strong> 收藏的餐廳
            </li>
            <li>
              <strong>{{ profile.Followings.length}}</strong> followings (追蹤者)
            </li>
            <li>
              <strong>{{ profile.Followers.length }}</strong> followers (追隨者)
            </li>
          </ul>
          <div>
            <button v-if="isFollowed === false" @click.prevent.stop="follow" type="submit" class="btn btn-primary">追蹤</button>
            <form v-else @submit.prevent.stop="unfollow" action="/following/72?_method=DELETE" method="POST" style="display: contents;">
              <button type="submit" class="btn btn-danger">取消追蹤</button>
            </form>
          </div>
        </div>
      </div>
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
    initialIsFollowed: {
      type: Boolean,
      required: true
    }
  },
  data ( ) {
    return {
      profile: this.initialProfile,
      isFollowed: this.initialIsFollowed
    }
  },
  methods: {
    follow() {
     this.isFollowed = true
    },
    unfollow() {
      this.isFollowed = false
    }
  }
}
</script>>