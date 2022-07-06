<template>
<div id="taskItem">
    <p>{{ taskTitle }} is <em> {{ isDone ? 'Done' : 'not done'}}</em> | <span class="icon"><i class="fas fa-pencil-alt"></i></span>  | <span class="icon"><i class="fas fa-trash"></i></span></p>
</div>   
</template>

<script>
export default {
    props: ['taskId', 'taskTitle', 'taskComplete'],
    data: () => ({
        id: 1,
        title: 'Learn Azure cloud',
        isDone: false
    }),
}
</script>

<style>
.fa-trash {
    color: red;
    cursor: pointer;
}
.fa-pencil-alt {
    color: orange;
    cursor: pointer;
}
</style>