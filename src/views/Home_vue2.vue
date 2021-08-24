<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <h3>
      You have <b> {{ todos.length }} </b> ToDos!!
    </h3>
  </div>

  <div>
    <input
      placeholder="Add a ToDo"
      type="text"
      v-model="newName"
      v-on:keyup.enter="addToDo"
    />
  </div>
  <ul>
    <li v-for="(todo, index) in todos" :key="index">
      <span>{{ todo.name }} </span>
      <button @click="deleteTodo(index)">X</button>
    </li>
    <!-- <li>
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
    </li> -->
  </ul>
</template>

<script>
// @ is an alias to /src
// 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
export default {
  data() {
    return {
      newName: '',
      todos: [
        {
          name: 'Deutsch Aufsatz schreiben',
        },
        {
          name: 'Fussball spielen',
        },
        {
          name: 'Online-Meeting',
        },
      ],
    };
  },
  methods: {
    addToDo() {
      console.log('Enter addToDo() ...');
      let aNewTodDo = {
        name: this.newName,
      };
      this.todos.push(aNewTodDo);
      this.newName = '';
    },
    deleteTodo(index) {
      this.todos.splice(index, 1);
    },
  },
};
</script>

<style scoped>
ul {
  list-style-type: none;
  padding: 0;
  width: 300px;
  margin: 20px auto 0;
}
li {
  border: 1px solid;
  display: flex;
  margin-bottom: 10px;
}
li span {
  flex-grow: 1;
}
input {
  width: 300px;
}
</style>
