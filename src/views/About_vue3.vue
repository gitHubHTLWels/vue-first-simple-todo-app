<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <!--
    <h3>
      You have <b> {{ todos.length }} </b> ToDos!!
    </h3>
    -->
  </div>

  <!--
  <div>
    <input
      placeholder="Add a ToDo"
      type="text"
      v-model="newName"
      v-on:keyup.enter="addToDo"
    />
  </div>
  -->
  <ul>
    <!--
    <li v-for="(todo, index) in todos" :key="index">
      <span>{{ todo.name }} </span>
      <button @click="deleteTodo(index)">X</button>
    </li>
    -->
    <li>
      <span>One </span>
      <button>X</button>
    </li>
    <li>
      <span>Two </span>
      <button>X</button>
    </li>
    <li>
      <span>Three </span>
      <button>X</button>
    </li>
  </ul>
</template>

<script>
import { ref } from 'vue';

export default {
  setup() {
    //const swearwords = ['Hausübung', 'lernen', 'Schule'];
    let newName = ref('');
    let todos = ref([
      {
        name: 'Deutsch Aufsatz schreiben',
      },
      {
        name: 'Fussball spielen',
      },
      {
        name: 'Online-Meeting',
      },
    ]);

    function addToDo() {
      console.log('Enter addToDo() ...');
      if (newName.value.length > 0) {
        let aNewTodDo = {
          name: newName.value,
        };
        todos.value.push(aNewTodDo);
        newName.value = '';
      }
    }

    function deleteTodo(index) {
      todos.value.splice(index, 1);
    }

    return {
      newName,
      todos,
      addToDo,
      deleteTodo,
    };
  },
};
</script>