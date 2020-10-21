<template>
  <div>
    <h1>Викторина</h1>
    <hr>

    <QuestionList 
      v-bind:questions="questions"
    />

  </div>
</template>

<script>
import QuestionList from '@/components/QuestionList';

export default {
  data() {
    return {
      questions: [
        { id:1, title: 'Какова скорость света?', var1: '~300 тыс км/ч', var2: '~500 тыс км/ч', answer: '~300 тыс км/ч' },
        { id:2, title: 'Какая таблетка в "Матрице" открывала правду?', var1: 'Синяя', var2: 'Красная', answer: 'Красная' },
        { id:3, title: 'Киты могут не спать 100 дней и не есть до 10-ти месяцев?', var1: 'Да', var2: 'Нет', answer: 'Да' },
      ]
    }
  },
  components: {
    QuestionList
  }
}
</script>