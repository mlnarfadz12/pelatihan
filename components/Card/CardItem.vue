<template>
  <div
    v-if="!tasks.isDone || ok"
    :class="[
      'item-task d-flex align-items-start border-bottom pt-3 pb-4',
      isGrid ? 'col-12 col-md-6 col-lg-4' : 'col-12',
    ]"
  >
    <input
      type="checkbox"
      name="status"
      id="task"
      class="me-2 mt-2"
      :checked="tasks.isDone"
      v-model="tasks.isDone"
    />
    <div
      :class="[
        'd-flex flex-column',
        tasks.isDone ? 'text-decoration-line-through fst-italic' : '',
      ]"
    >
      <div class="title-task mb-1">{{ tasks.title }}</div>
      <div class="badge bg-success">{{ tasks.category }}</div>
      <div class="description-task small text-muted">
        {{ tasks.description }}
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    tasks: Object,
    ok: false,
    isGrid: {
      type: Boolean,
      required: true,
      default: false,
    },
  },
};
</script>
