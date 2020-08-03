<template>
  <div>
    <button @click="handleClick">click</button>
    {{ storeCount }}
    {{ countDouble }}
    {{ countAdd(3) }}
  </div>
</template>

<script>
import { mapState, mapGetters, mapMutations } from "vuex";
export default {
  data(){
    return {
      count : 100
    }
  },
  computed: {
    ...mapState({
      storeCount : 'count'
    }),
    ...mapGetters(['countAdd','countDouble'])
  },
  methods: {
    ...mapMutations(['countIncrement']),
    handleClick(){
      this.$store.commit('countIncrement',Math.random()*10)
    }
  }
}
</script>

<style>

</style>