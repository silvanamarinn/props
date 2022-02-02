<template>
  <div id="app">
    <section>
      <label for="txt_task">Tarea</label>
      <input id="txt_task" type="text" v-model="task" placeholder="ingresar nueva tarea"/>
      
      <button @click="addTask">Añadir</button>
      
    </section>
    <section>
      <Lista :tasks="tasks" :deleteTaks="deleteTaks" />
    </section>
  </div>
</template>

<script>
import Lista from '@/components/Lista.vue';

export default {
  name: 'App',
  components: {
    Lista
  },
    data() {
    return {
      task: "",
      tasks: [],
    };
  },
  methods: {
    addTask() {
      const { task } = this;
      this.tasks.push(task);
    },
    deleteTaks(indexTask) {
      this.tasks.splice(indexTask, 1);
    },
  },
};
</script>

<style>
#app {
  font-family: 'Courier New', Courier, monospace;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
  font-size: 30px;
}

label {
  font-weight: 700;
  margin: 0.3rem
}

button {
  padding: 0.1rem 0.75rem;
  margin: 0rem 0.3rem;
  border-radius: 8px;
  border: 1px solid rgb(204, 202, 202);
  background-color: white;
}

ul {
  font-weight: 700;
}

section {
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
