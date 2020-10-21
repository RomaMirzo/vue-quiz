<template>
  <div>
    <ul>
      <QuestionItem 
        v-for="question of questions"
        v-bind:question="question"
        v-bind:key="question.id"
      />
    </ul>
  </div>
</template>

<script>
import QuestionItem from '@/components/QuestionItem';

export default {
  props: ['questions'],
  components: {
    QuestionItem
  }
}
</script>

<style scoped>
  ul {
    list-style: none;
    margin: 0;
    padding: 0;
  }
</style>

