<template>
  <div>
  <ul>
      <li v-for="(message, index) in messages" :key="message.id">
        <router-link :to="`/home/message/detail/${message.id}`">{{message.title}}</router-link>
        <button @click="pushShow(message.id)">push查看</button>
        <button @click="replaceShow(message.id)">replace查看</button>
      </li>
    </ul>
    <button @click="$router.back()">返回</button>
    <hr>
    <router-view></router-view>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        messages:[]
      }
    },

    mounted () {
      //模拟ajax请求 从后台获取数据
      setTimeout(() => {
        const messages = [
          {
            id: 1,
            title: 'message001'
          },
          {
            id: 2,
            title: 'message002'
          },
          {
            id: 3,
            title: 'message003'
          },
          {
            id: 4,
            title: 'message004'
          }
        ]
        this.messages= messages
      },1000)
    },

    methods: {
      pushShow(id) {
        this.$router.push(`/home/message/detail/${id}`)

      },

      replaceShow(id) {
        this.$router.replace(`/home/message/detail/${id}`)
      }
    }
  }
</script>

<style>

</style>
