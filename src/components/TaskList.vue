<template>
    <div class="main">
        <h3 class="title is-2">My TaskList</h3>
        <div id="taskAddForm">
            <input class="input is-primary is-focused" type="text" placeholder="Add Task" v-model="newTask" /><br/>
            <button class="button is-success" @click="addTask()">Add Task</button>
        </div>
        <p v-if="taskItems == 0" id="noItems">No tasks to show</p>
        <div v-else id="allTasks">
            <TaskItem :titleTask="newTask" />
        </div>   
    </div>
</template>

<script>
import TaskItem from './TaskItem.vue';
export default {
    data: () => ({
        newTask: "",
        taskItems: [],
    }),
    methods: {
        addTask: function () {
            if (this.newTask == "")
                console.log("button click");
            else {
                console.log(`button clicked with value of ${this.newTask}`);
                this.taskItems.push({taskId: 1, taskTitle: this.newTask, taskComplete: false})
            }
            this.newTask = "";
        }
    },
    components: { TaskItem }
}
</script>

<style>
h3 {
    font-family: 'Titillium Web', sans-serif;
}
button {
    margin: .5rem;
}
#taskAddForm {
    margin: auto;
    width: 840px;
    padding: .7rem;
    
}
#noItems {
    color: grey;
}
</style>