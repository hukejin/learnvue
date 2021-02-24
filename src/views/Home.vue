<template>
  <div class="home">
    <p>展示生命周期</p>
    <button @click="show">点击我</button>
    <ul>
      <li v-for="(item,index) in cycle" :key="index">{{item}}</li>
    </ul>
    <timeline @itemdown="itemclick"></timeline>
  </div>
</template>

<script>
  import timeline from '@/components/timeline'
// @ is an alias to /src
export default {
  name: 'Home',
  data () {
    return {
      cycle: [],
      index: 1
    }
  },
  beforeCreate () {
    console.log('beforeCreate')
  },
  created () {
    console.log('created')
  },
  beforeMount () {
    console.log('beforeMount')
  },
  mounted () {
    console.log('mounted')
  },
  beforeUpdate () {
    console.log('beforeUpdate')
  },
  updated () {
    console.log('updated')
  },
  beforeDestroy () {
    console.log('beforeDestroy')
  },
  destroyed () {
    console.log('destroyed')
  },
  components: {
    timeline
  },
  methods: {
    show () {
      this.index = this.index + 1
      this.cycle.push(this.index)
      this.$nextTick(() => { console.log('我是什么') })
    },
    itemclick(index){
      alert("点击了,"+index)
    }
  }
}
</script>
