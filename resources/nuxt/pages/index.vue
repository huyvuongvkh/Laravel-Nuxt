<template>
  <div>
    <p>SPA in Laravel</p>
    <ul>
        <li v-for="(user,index) in users" :key="index">
            {{ user }}
            <nuxt-link :to="`/user/${index}`">click</nuxt-link>
         </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "IndexPage",
  async created() {
        this.users = await this.$axios.$get('testAPI');
    },
    data() {
      return {
        users: []
      }
    },
};
</script>
