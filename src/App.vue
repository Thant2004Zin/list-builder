<template>
    <div>
        <h1>{{ title }}</h1>
        <ul>
            <li v-for="(list,index) in lists" v-bind:key="index">
                {{ list }}
                <button v-on:click="Del(index)">Del</button>
            </li>
        </ul>


        <form action="" v-on:submit.prevent="addList">
            <input type="text" v-model="input" required>
            <button>Add</button>
        </form>
    </div>
</template>

<script>
    export default {
      data() {
        return {
          title: "List Builder",
          lists :  [
              "To eat",
              "To sleep",
          ]
        }
      },
        methods:{
          addList(){
              this.lists.push(this.input)
              this.input = null
          },
          Del(index){
              this.lists.splice(index,1)
          }
        }
    }
</script>

<style>

    @import "boo";

</style>