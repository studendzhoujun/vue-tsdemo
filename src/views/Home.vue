<template>
  <div class="home">
    <HelloWorld :msg="msg"/>
    <todo-list :sourceData="datas" @send-item="getItem"></todo-list>
    <input v-model="inputValue"></input>
    <button @click="addItem">add</button>
  </div>
</template>

<script lang="ts">
// @ is an alias to /src
import { Component, Vue } from 'vue-property-decorator';
import HelloWorld from '@/components/HelloWorld.vue';
import todoList from '@/components/todoList.vue';
@Component({
  components: {
    HelloWorld,
    todoList,
  },
})
export default class App extends Vue {
  private msg: string = 'this is a home page';
  private datas: any[] = ['a', 'b', 'c'];
  private inputValue: string = '';
  private getItem(item:string){
      console.log('getItem',item)
  }
  private addItem(){
    console.log(this.inputValue);
    if(this.inputValue){
      this.datas.push(this.inputValue);
      this.inputValue = '';
    }
  }
}
</script>
<style lang="scss">
input{
  width:100%;
  height:20px;
  border: 1px solid #909;
}
button{
  width:30px;
  height:50px;
  border:1px solid #909;
}
</style>
