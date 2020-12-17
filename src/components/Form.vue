<template>
<div class="form-area">
  <input v-model="name" type="text">
  <button @click="criarNome">Adicionar</button>
</div>
</template>

<script>
export default {
  name:'Form',

  data(){
    return{
      name:'',
    }
  },

  methods:{
    criarNome: function(){
      if(this.name ===''){
        return
      }
      this.$emit("criar",{nome : this.name})
      this.name = ''
      
    }
  }
}
</script>

<style lang='scss' scoped>
.form-area{
  display: flex;
  align-items: center;
  justify-content: center;

  width: 70%;
  margin:30px auto;
  border-radius: 10px;

  height: 50px;

    &{
      input{
        height:40px;
        width: 300px;
        border-radius: 5px 0 0 5px;
        padding: 0 0 0 10px;
        font-size: 12pt;
        
      }
      button{
        height: 40px;
        width: 100px;
        
        border-radius:0 5px 5px 0;
        cursor: pointer;

        background: rgb(202, 9, 202);
        font-size: 11pt;
        font-weight: bold;
        color: white;
        
        transition: .3s;
        &:hover{
          transform: translateX(-10px);
        }
      }
    }

}
</style>