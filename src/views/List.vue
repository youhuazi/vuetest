<template>
    <div>
      <ul>
        <li v-for="(item,index) in listPage" :key="index">
          {{item.title}}
          {{item.content}}
        </li>
      </ul>
    </div>
</template>

<script>
import store from '@/store'
export default {
  name: 'List',
  store,
  computed: {
    listPage () {
      return store.state.lists
    }
  }
}
</script>

<style scoped>

</style>
