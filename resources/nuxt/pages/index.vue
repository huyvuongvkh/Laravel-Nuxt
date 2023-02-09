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
  async asyncData({ app }) {
        const users = await app.$axios.$get('testAPI');
        return { users };
    },
    data() {
      return {
        users: []
      }
    },
};
</script>
