<template>
  <div class="tasks">
    <div class="card" style="width: 24rem;">
      <div class="card-header">
        Tasks
      </div>
        <task-card id="taskCard" v-for="task in tasks" :key="task.id" :task="task" />
    </div>
  </div>
</template>

<script>
import TaskCard from '../components/TaskCard.vue'
import TaskService from '../services/TaskService.js'
export default {
  name: 'TasksList',
  components: {
    TaskCard
  },
  data () {
    return {
      tasks: null
      /* [{
          id: 1,
          title: 'Task 1',
          description: 'Description for task 1',
          location: 'Valletta',
          date: '1st of Jan',
          time: '12:00'
        },
        {
          id: 2,
          title: 'Task 2',
          description: 'Description for task 2',
          location: 'Valletta',
          date: '1st of Jan',
          time: '12:00'
        },
        {
          id: 3,
          title: 'Task 3',
          description: 'Description for task 3',
          location: 'Valletta',
          date: '1st of Jan',
          time: '12:00'
        }
      ] */
    }
  },
  created () {
    TaskService.getTasks()
      .then(response => {
        this.tasks = response.data
      })
      .catch(error => {
        console.log('ERRORS' + error)
      })
  }
}
</script>

<style scoped>
  .tasks{
    /*border: 2px solid orange;*/
    width: 95%;
    margin: auto;
  }

  .card{
    margin: auto;
  }
</style>
