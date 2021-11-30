<template>
  <div id="app">
      <!-- <UserCard /> -->
      <SearchUsers />
  </div>
</template>

<script>   
  // import UserCard from '@/components/UserCard.vue'
  import SearchUsers from '@/components/SearchUsers.vue'
  export default {
    name: 'App',
    components: { 
      SearchUsers
    }
  }
</script>

