<template>
  <div>
    <h1 style="color:white;">Quais são seus planos pra hoje?</h1>
    <Form @criar="criando($event)" :name="name"/>

    <div v-for="task in tasks" :key="task.id">
      <Cards @deletar="deletando($event)"  :name="task.name" :id="task.id"/>
    </div>

  </div>
</template>

<script>
import Form from './Form'
import Cards from './Cards'
export default {
  components:{
    Form,
    Cards,
  },
  
  data(){
    return{
      tasks:[
        {
          name:'sad',
          id:Date.now()
        }
      ]
    }
  },

  methods:{
    criando:function($event){
      var taskName = $event.nome

     this.tasks.push({name:taskName,id:taskName+Date.now()})
    },

    deletando:function($event){
      const id = $event.id

      const finded = this.tasks.find(task => id === task.id)
      if(finded){
        const newTasks = this.tasks.filter(task => task !== finded)
         console.log(finded.name)
         this.tasks = newTasks
      }
      

    }
  }

}
</script>


<style scoped>

</style>
