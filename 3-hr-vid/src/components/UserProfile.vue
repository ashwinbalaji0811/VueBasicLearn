<template>
    @{{ user.userName}} - {{fullName}}
    <strong>Followers: </strong> {{ followers }}
    <button @click="followUser"> Follow </button>
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
        admin: true
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
}
</script>