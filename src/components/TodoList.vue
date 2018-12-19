<template>
 <div>
     <BaseInputText
        v-model="newTodoText"
        placeholder="New todo"
        v-on:keydown.enter="addTodo"
     />
     <ul v-if="todos.length">
       <TodoListItem
         v-for="todo in todos"
         v-bind:key="todo.id"
         v-bind:todo="todo"
         v-on:remove="removeTodo"
       />
     </ul>
       <p v-else>
         리스트를 추가해 주세요!
       </p>
 </div>
</template>

<script>
/* eslint-disable */

  import BaseInputText from './BaseInputText.vue'
  import TodoListItem from './TodoListItem.vue'

  let nextTodoId = 1

  export default {
    components: {
      BaseInputText,
      TodoListItem,
    },
    data() {
      return {
        newTodoText: '',
        todos: [
          {
            id: nextTodoId++,
            text: 'Learn Vue'
          },
          {
            id: nextTodoId++,
            text: 'Learn about single file components'
          },
          {
            id: nextTodoId++,
            text: 'Fail in love'
          }

        ]
      }
    },
    methods: {
      addTodo : function(){
        //trim("   111   ") => "111   "
        const trimmedText = this.newTodoText.trim()
        if (trimmedText) {
          this.todos.push({
            id : nextTodoId++,
            text : trimmedText,
          })
          this.newTodoText = ''
        }
      },
      removeTodo : function(idToRemove) {
        this.todos = this.todos.filter(todo => {
          return todo.id !== idToRemove
        })
      }
    }
  }


</script>
