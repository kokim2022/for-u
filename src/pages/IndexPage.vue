<template>
  <div>
    Lorem ipsum dolor sit amet consectetur adipisicing elit. Beatae repellendus, repellat quaerat impedit et laboriosam deleniti fugit praesentium, dolor officia inventore iure magni laborum illum, minus nulla necessitatibus doloribus! Porro!
  </div>
</template>

<script lang="ts">
import { Todo, Meta } from 'components/models';
// import ExampleComponent from 'components/ExampleComponent.vue';
import { defineComponent, ref } from 'vue';

export default defineComponent({
  name: 'IndexPage',
  // components: { ExampleComponent },
  setup () {
    const todos = ref<Todo[]>([
      {
        id: 1,
        content: 'ct1'
      },
      {
        id: 2,
        content: 'ct2'
      },
      {
        id: 3,
        content: 'ct3'
      },
      {
        id: 4,
        content: 'ct4'
      },
      {
        id: 5,
        content: 'ct5'
      }
    ]);
    const meta = ref<Meta>({
      totalCount: 1200
    });
    return { todos, meta };
  }
});
</script>
