<template>
  <div class="user-profile">
      <div class="user-profile_user-panel">
          <h1 class="user-profile_username">@{{ user.userName }}</h1>
          <div class="user-profile_admin-badge" v-if="user.isAdmin">
              Admin
          </div>
          <div class="user-profile_follower-count">
              <strong>Followers: </strong> {{ followers }}
          </div>
      </div>
  </div>
</template>

<script>
export default {
    data(){
    return{
      followers: 0,
      user: {
        id: 1,
        userName: 'sann0409',
        firstName: 'Sannia',
        lastName: 'Sajive',
        email: 'sanniasajive0409@gmail.com',
        isAdmin: true
      }
    }
  },
  watch: {
    followers(newFollowerCount, oldFollowerCount) {
      if (oldFollowerCount < newFollowerCount){
        console.log(`${this.user.userName} has gained a follower!`)
      }
    }
  },
  computed: {
    fullName() {
      return `${this.user.firstName} ${this.user.lastName}`;
    }
  },
  methods: {
    followUser() {
      this.followers++;
    }
  },
  mounted() {
    this.followUser();
  }
};
</script>

<style scoped>
.user-profile {
    display: grid;
    grid-template-columns: 1fr 3fr;
    width: 100%;
    padding: 50px 5%;
}
.user-profile_user-panel {
    display: flex;
    flex-direction: column;
    margin-right: 50px;
    padding: 20px;
    background-color: aquamarine;
    border-radius: 5px;
    border: 1px solid #dfe3e8;
}
.user-profile_admin-badge{
    background-color: rebeccapurple;
    color: burlywood;
    border-radius: 5px;
    margin-right: auto;
    padding: 0 10px;
    font-weight: bold;
}
h1 {
    margin: 0;
}
</style>