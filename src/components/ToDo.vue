<template>
  <div >
    <div class="container main">
      <h1> Todo List </h1>
      <div class="row">
        <div class="col-12" id="input">
          <input class="form-control" type="text" v-model="task" ><input @click="addTask()" type="button" class="btn" id = "inputbtn" value="Add Task">
        </div>

        <div class="col-12" id="tasks">
          <h3> To be done({{tasks.length}})</h3>
          <ul>
            <li  v-for="(t, index) in tasks" :key="index" >{{t}}<button class="btn" @click="removeTask(t)"><i class="fa fa-trash" aria-hidden="true"></i></button><button class="btn" @click="doneTask(t)"><i class="fa fa-check" aria-hidden="true"></i></button></li>

          </ul>
        </div>

        <div class="col-12" id="completed">
          <h3> Completed({{completed.length}})</h3>
          <ul>
            <li  v-for="(t, index) in completed" :key="index" >{{t}}<button class="btn" @click="deleteTask(t)"><i class="fa fa-trash" aria-hidden="true"></i></button></li>

          </ul>
        </div>
      </div>
    </div>

    <br><br>



  </div>
</template>
<script>
export default {
  name: 'ToDo',
  data() {
    return {
      tasks: [],
      completed: [],
      task: '',
    };
  },

  methods: {
    addTask() {
      if (this.task.length > 0) {
        this.tasks.push(this.task)
        this.task = ""
      }
    },

    removeTask(index) {
      this.tasks.splice(index, 1)
    },

    doneTask: function (index) {
      this.completed.push(this.tasks.splice(index, 1).toString())
    },

    deleteTask(index) {
      this.completed.splice(index, 1)
    },

  }
};

</script>

<style>

#input {
  display: flex;
  flex-direction: row;

}

.main{
  width: 50% !important;
  align-items: center;
}

li{
  width: 100%;
  text-align: left;
  margin-top: 20px;
  font-size: 20px;
}

.btn{
  float: right;
  margin-left: 10px;
}

.btn:hover, btn:focus{
  border: none;
}

#inputbtn{
  background-color: #32ddae !important;
}

.fa{
  color: #32ddae !important;
}

#tasks{
  margin-top: 30px;
}
</style>