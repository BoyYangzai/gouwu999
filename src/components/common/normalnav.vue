<template>
    <div class="normalnav">
<div class='eachnav' v-for="(item,index) in title" :key="index" @click="activechange(index)" :class="{active:index==currentindex}">
{{item}}
</div>
    </div>
</template>
<script>
export default {
  setup() {
    
  },
  props:{
    title:Array
  },
  data(){
    return{
      currentindex:0
    }
  },
  methods:{
    activechange(index){
      this.currentindex=index;
      this.$emit('change',index)
    }
  }
}
</script>
<style scoped>

.normalnav{
  display: flex;
  box-sizing: content-box;
  text-align: center;
  color: rgba(138, 136, 136, 0.842);
  font-weight: 700;
  font-size: 23px;
  box-shadow: 0 0 4px 1px rgba(0,0,0,0.1);
}
div{
  line-height: 50px;
  height: 50px;
}
.active{
  color:rgba(206, 104, 8, 0.876);
  border-bottom: 7px solid rgba(206, 104, 8, 0.876) ;
}
.eachnav{
  flex: 1;
}
</style>