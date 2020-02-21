<template>
  <div class="inputBox shadow">
      <!-- v-model은 input에 입력된 텍스트를 동적으로 vue 인스턴스에 mapping -->
      <input type="text" v-model="newTodoItem" v-on:keyup.enter="addTodo">
      <span class="addContainer" v-on:click="addTodo">
          <i class="fas fa-plus addBtn"></i>
      </span>
  </div>
</template>

<script>
export default {
    data: function() {
        return {
            newTodoItem: ""
        }
    },
    methods: {
        addTodo: function() {
            if(this.newTodoItem !== ''){
                var obj = {
                    completed: false,
                    item: this.newTodoItem
                };
                // 저장하는 로직 localStorage.setItem('key','value')
                localStorage.setItem(this.newTodoItem, JSON.stringify(obj));
                this.clearInput();
            }
            
        },
        clearInput: function() {
            this.newTodoItem = '';
        }
    }
}
</script>

<style scoped>
input:focus {
    outline: none;
}
.inputBox {
    background: white;
    height: 50px;
    line-height: 50px;
    border-radius: 5px;
}
.inputBox input {
    border-style: none;
    font-size: 0.9rem;
}
.addContainer {
    float: right;
    background: linear-gradient(to right, pink, #8763FB);
    display: block;
    width: 3rem;
    border-radius: 0 2px 2px 0;
}
.addBtn {
    color: white;
    vertical-align: middle;
}
</style>