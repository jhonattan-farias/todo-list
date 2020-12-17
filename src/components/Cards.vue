<template>
      <div :class="{'card-done':done===true,'card':done=== false}">
            <img @click="taskDone"  src="../assets/verified.png" alt="">
          <div class="task-area"><p>{{name}}</p></div>   

          <div class="button-area"><button @click="deletar">Deletar</button></div>
      </div>
</template>

<script>
export default {
    data(){
        return{
            done:false,
        }
    },

props:{
    name:String,
    id:Number
},
methods:{
    deletar:function(){
        this.$emit('deletar',{id:this.id})
    },
    taskDone:function(){
        this.done = !this.done
    }
}

}
</script>

<style scoped lang='scss'>
.card{
    display: flex;
    margin: 20px auto;
    width: 550px;
    height: 50px;
    border-radius: 10px;
    background: white;
    transition: .2s;
    img{

            align-self: center;
            cursor: pointer;
            height: 30px;
            width: 30px;
            margin-left: 10px;
            border-radius: 50%;
            opacity: .8;

            background:rgb(0, 255, 0);

            &:hover{
                opacity: 1;
            }
        }

    .task-area{
        padding: 10px;
        display: flex;
        align-items: center;
        justify-content:space-around;
        width: 50%;
        p{
        }
    }
    .button-area{
        padding: 10px;
        display: flex;
        align-items: center;
        justify-content: flex-end;
        width: 50%;
        button{
            cursor: pointer;
            height: 40px;
            width: 80px;
            border-radius: 4px;

            font-size:11pt;
            font-family: 'Open Sans', sans-serif;
            font-weight: bold;
            color: white;

            background: red;
        }
    }
}


.card-done{
    display: flex;
    margin: 20px auto;
    width: 550px;
    height: 50px;
    border-radius: 10px;
    background: white;
    opacity: .2;
    transition: .2s;

    img{

            align-self: center;
            cursor: pointer;
            height: 30px;
            width: 30px;
            margin-left: 10px;
            border-radius: 50%;
            opacity: 1;

            background:rgb(0, 255, 0);

            &:hover{
                opacity: 1;
            }
        }

    .task-area{
        padding: 10px;
        display: flex;
        align-items: center;
        justify-content:space-around;
        width: 50%;
        p{
        }
    }
    .button-area{
        padding: 10px;
        display: flex;
        align-items: center;
        justify-content: flex-end;
        width: 50%;
        button{
            cursor: pointer;
            height: 40px;
            width: 80px;
            border-radius: 4px;

            font-size:11pt;
            font-family: 'Open Sans', sans-serif;
            font-weight: bold;
            color: white;

            background: red;
        }
    }
}
</style>