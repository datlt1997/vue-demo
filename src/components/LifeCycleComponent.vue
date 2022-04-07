<template>
  <div>
      <!-- <p>Ask a yes/no question</p>
      <input v-model="question">
      <p>{{ answer }}</p> -->
      <input ref="input">
      <ul>
          <li v-for="(item, key, index) in list" :key=key ref="items">{{ item.name}}</li>
      </ul>
  </div>
</template>

<script>
export default {
    data() {
        return {
            list : [
                {'name' : 'abc'},
                {'name' : 'xys'},
                {'name' : 'ndb'}
            ]
        }
    },
    // watch: {
    //     question(newQuestion, oldQuestion) {
    //         if(newQuestion.indexOf('?') > -1) {
    //             this.getAnswer()
    //         }
    //     },
    //     deep: true
    // },
    // methods : {
    //     async getAnswer() {
    //         this.answer = 'thinking'
    //         try {
    //             const res = await fetch('https://yesno.wtf/api')
    //             this.answer = (await res.json()).answer
    //         } catch (error) {
    //             this.answer = 'errorrr...'
    //         }
    //     }
    // },
    mounted() {
        // this.$refs.input.focus
        console.log(this.$refs.items)
    }
}
</script>

<style>

</style>