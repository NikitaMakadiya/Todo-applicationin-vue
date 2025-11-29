<template>
  <div class="continer">
    <h1>TodoList</h1>

    <div class="input-wrapper">
      <input type="text" placeholder="" v-model="task" class="text-input" />
      <button @click="additem">Add</button>
    </div>
    <div class="data" v-for="task in tasks" :key="task.id">
      <div>
        <input v-model="task.check" type="checkbox" name="check" />
      </div>

      <div :class="{ complited: task.check }">{{ task.name }}</div>
      <div @click="deletetask(task.id)" class="deletbtn">delete</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "TodoList",

  data() {
    return {
      task: "",

      tasks: [
        { id: 1, name: "go to market", check: false },
        { id: 2, name: "go to school", check: false },
        { id: 3, name: "go to office", check: true },
      ],
    };
  },

  methods: {
    additem() {
      if (this.task !== "") {
        this.tasks.push({ id: Date.now(), name: this.task, check: false });
        this.task = "";

        console.log(this.tasks);
      }
    },
    deletetask(id) {
      this.tasks = this.tasks.filter((t) => t.id !== id);
    },
  },
};
</script>
<style>
.continer {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.input-wrapper {
  display: flex;
  gap: 20px;
  margin-bottom: 10px;
}
.deletbtn {
  cursor: pointer;
  color: red;
}
.text-input {
  width: 250px;
  height: 25px;
  font-size: large;
}
.data {
  width: 300px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px;
  border-bottom: 1px solid #ddd;
  margin-top: 10px;
}
.continer {
  width: 500px;
  padding: 20px;
  text-align: center;
}
.complited {
  text-decoration: line-through;
}
</style>
