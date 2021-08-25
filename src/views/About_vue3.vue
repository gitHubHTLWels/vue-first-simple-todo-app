<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <h3>
      You have <b> {{ todosCount }} </b> ToDos!!
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
  </ul>
</template>

<script>
import { ref, computed, watch } from 'vue';

export default {
  setup() {
    const swearwords = ['Hausübung', 'lernen', 'Schule'];

    let todosCount = computed(() => {
      return todos.value.length;
    });
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

    watch(newName, (newVal) => {
      console.log('New Val ' + newVal.value);
      if (swearwords.includes(newVal)) {
        newName.value = '';
      }
    });

    return {
      newName,
      todos,
      addToDo,
      deleteTodo,
      todosCount,
    };

    /*    return {
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
      swearwords: ['Hausübung', 'lernen', 'Schule'],
    };
  },
  methods: {
    addToDo() {
      console.log('Enter addToDo() ...');
      if (this.newName.length > 0) {
        let aNewTodDo = {
          name: this.newName,
        };
        this.todos.push(aNewTodDo);
        this.newName = '';
      }
    },
    deleteTodo(index) {
      this.todos.splice(index, 1);
    },
  },
  watch: {
    newName(newValue) {
      console.log('New Val ' + newValue);
      if (this.swearwords.includes(newValue)) {
        this.newName = '';
      }
    },
  },
}; */
  },
};
</script>