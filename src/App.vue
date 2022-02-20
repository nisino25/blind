<template>
  <div style="width: 25%; position: absolute;top: 45%;left: 50%;-ms-transform: translateX(-50%) translateY(-50%);-webkit-transform: translate(-50%,-50%);transform: translate(-50%,-50%); border-color:green ">
    Algorithm:   {{alg}}
    <br>
    <button @click="shuffle()">shuffle</button>
  </div>
</template>


<script>

export default {
  // components:{
  //   ToggleButton,
  // },
  
  name: 'App',
  components: {
  },  
  data(){
    return{
      alg: '',
      list: [],
      darkMode: undefined,
      showingScore: false,
      searchDate: undefined,
      isFetchingData: false,
      gameData: undefined,
      displayDate: undefined,
      beforeEdit: undefined,
      showingDate: undefined,
      weekDay: ('Sun','Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat'),
      autoRefresh: false,
      todaysDate: (new Date()).getMonth()+1 + '-' + (new Date()).getDate() ,
      yesterdayDate: (new Date(new Date().setDate(new Date().getDate() - 1))).getMonth()+1 + '-' + (new Date(new Date().setDate(new Date().getDate() - 1))).getDate(), 
      twoDaysAgoDate: (new Date(new Date().setDate(new Date().getDate() - 2))).getMonth()+1 + '-' + (new Date(new Date().setDate(new Date().getDate() - 2))).getDate(),
      tomorrowsDate: (new Date(new Date().setDate(new Date().getDate() +1))).getMonth()+1 + '-' + (new Date(new Date().setDate(new Date().getDate() +1))).getDate(),
      afterTomorrowsDate: (new Date(new Date().setDate(new Date().getDate() +2))).getMonth()+1 + '-' + (new Date(new Date().setDate(new Date().getDate() +2))).getDate(),
      updateCount:0,
      hasFailed: false,
      fireData:[],
      userNum: 0,
    }
  },
  methods:{
    shuffle(){
      this.alg = ''
      this.list = ['q','w','e','r','t','u','i','o','p','a','b','s','d','f','g','h','j','k','l','x','c','v','n','m']
      let lastnum = 100


      for (var i=1;i<=10; i++) {
        let randomnum = Math.floor(Math.random() * 24)
        if(randomnum == lastnum ){
          i--
        }else{
          this.alg = this.alg + this.list[randomnum]
          lastnum = randomnum
          if(i % 2 === 0  ){
            this.alg = this.alg + ': '
          }
        }

      }
      this.alg = this.alg.toUpperCase()

    }
  },
  created() {
    this.shuffle()
  },
  mounted(){
    
  },
  watch:{
    
  },
}
</script>