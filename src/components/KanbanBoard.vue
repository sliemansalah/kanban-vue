<template>
  <div class="board">
    <div class="row">
        <div class="col-md">
          <task-lane id="todo" title="Todo" :items="todoItems"></task-lane>
        </div>
        <div class="col-md">
          <task-lane id="inProgress" title="In progress" :items="inProgressItems"></task-lane>
        </div>
          <div class="col-md">
          <task-lane id="complete" title="Complete" :items="completeItems"></task-lane>
        </div>
          <div class="col-md">
          <task-lane id="test" title="Test" :items="testItems"></task-lane>
        </div>
        <div class="col-md">
          <task-lane id="done" title="Done" :items="doneItems"></task-lane>
        </div>
    </div>
  </div>
</template>

<script>
import { mapState } from 'vuex';
import TaskLane from './TaskLane';

export default {
  name: 'KanbanBoard',
  components: {
    'task-lane': TaskLane
  },
  computed: mapState({
    todoItems: s => s.items.todo,
    inProgressItems: s => s.items.inProgress,
    completeItems: s => s.items.complete,
    testItems: s => s.items.test,
    doneItems: s => s.items.done
  })
};
</script>
