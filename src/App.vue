<script>
export default {
  data() {
    return {
      myTitle: "My todo list",
      todoItems: [
        { name: "wash", description: "Wash dishes at 2pm" },
        { name: "wash", description: "Wash car at 3pm" },
        { name: "read", description: "Read for an exam" },
      ],
      name: "",
      newTodoItem: {
        name: "",
        description: "",
      },
    };
  },
  methods: {
    addTodo() {
      this.todoItems.push(this.newTodoItem);
    },
  },
};
</script>

<template>
  <p>{{ myTitle }}</p>

  {{ newTodoItem }}
  <ul>
    <li class="capitalize" v-for="(item, index) in todoItems" :key="index">
      {{ index + 1 }}. {{ item.name }} {{ item.description }}
    </li>
  </ul>

  <input v-model="newTodoItem.name" />
  <input v-model="newTodoItem.description" />
  <button v-on:click="addTodo">Add Todo</button>
</template>

<style scoped>
.capitalize {
  text-transform: capitalize;
}
</style>
