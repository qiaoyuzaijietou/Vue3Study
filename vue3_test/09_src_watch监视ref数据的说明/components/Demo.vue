<template>
  <h2>当前求和为：{{ sum }}</h2>
  <button @click="sum++">点我加一</button>
  <hr />
  <h2>当前的信息为：{{ msg }}</h2>
  <button @click="msg += '！'">修改信息</button>
  <hr />
  <h2>姓名：{{ person.name }}</h2>
  <h2>年龄：{{ person.age }}</h2>
  <h2>薪资：{{ person.job.j1.salary }}k</h2>
  <button @click="person.name += '~'">修改姓名</button>
  <button @click="person.age++">修改年龄</button>
  <button @click="person.job.j1.salary++">修改薪资</button>
</template>

<script>
import { ref, reactive, watch } from "vue";
export default {
  name: "Demo",
  /* beforeCreate(){ 
    console.log('---boforeCreate---');
  }, */
  setup() {
    // 数据
    let sum = ref(0);
    let msg = ref("你好啊");
    let person = ref({
      name: "巧遇",
      age: 18,
      job: {
        j1: {
          salary: 20,
        },
      },
    });
    watch(sum,(newValue,oldValue)=>{
      console.log('sum变化了',newValue,oldValue);
    })
    watch(person,(newValue,oldValue)=>{
      console.log('person变化了',newValue,oldValue);
    },{
      deep:true
    })
    // 返回一个对象（常用）
    return {
      sum,
      msg,
      person,
    };
  },
};
</script>

