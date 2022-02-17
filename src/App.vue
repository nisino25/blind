<template>
  alg:{{alg}}
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
      this.list = ['q','w','e','r','t','u','i','o','p','a','s','d','f','g','h','j','k','l','x','c','v','n']


      for (var i=1;i<=10; i++) {
        this.alg = this.alg + ': : '
        console.log(this.list.length)

      }

      
      console.log('yos')
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