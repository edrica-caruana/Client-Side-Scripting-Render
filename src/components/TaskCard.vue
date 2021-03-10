<template>
  <ul class="list-group list-group-flush">
    <router-link class="task-link" :to="{name: 'TaskDetails', params: {id: task.id}}">
    <li class="list-group-item"><b>{{ task.title }}</b> on the {{task.date}} @ {{task.time}}</li>
    </router-link>
  </ul>
</template>

<script>
export default {
  name: 'Task Card',

  props: {
    task: Object
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}

a {
  color: #42b983;
}

.card{
    width: 95%;
    margin: auto;
}

.list-group-item{
  color: grey;
}

.list-group-item:hover{
  color: #42b983;
  box-shadow: 0 0 10px #000000;
  background-color: rgba(248, 247, 247, 0.979);
  text-decoration: none;
  outline: none;
}
</style>
