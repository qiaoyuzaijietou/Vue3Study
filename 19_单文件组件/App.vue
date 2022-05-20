<template>
    <div>
        <School></School>
        <Student></Student>
    </div>
</template>

<script>
// 引入组件
import School from './School'
import Student from './Student'
import Student1 from './Student.vue';
export default {
    name:'App',
    components:{
    School,
    Student,
    Student1
}
};
</script>