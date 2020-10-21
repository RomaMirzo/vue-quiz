<template>
  <div class="container">
    <li>
      {{question.title}} <br>

      <div class="quest">
        <button 
          v-on:click="setStyle1"
        >{{question.var1}}</button>
        <button
          v-on:click="setStyle2"
        >{{question.var2}}</button>
      </div>

    </li>
  </div>
</template>

<script>
  export default {
    props: {
      question: {
        type: Object,
        required: true
      }
    },
    methods: {
      setStyle1() {
        if(this.blockVar1) return;
        if(this.question.var1 === this.question.answer) {
          event.target.classList.add('trueAnswer');
        } else {
          event.target.classList.add('falseAnswer');
        }
        this.blockVar2 = true;
      },
      setStyle2() {
        if(this.blockVar2) return;
        if(this.question.var2 === this.question.answer) {
          event.target.classList.add('trueAnswer');
        } else {
          event.target.classList.add('falseAnswer');
        }
        this.blockVar1 = true;
      }
    },
    computed: {

    }
  }
</script>

<style scoped>
  .container {
    margin: 0 auto;
    max-width: 500px;
  }
  li {
    border: 1px solid #ccc;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    padding: .5rem 2rem;
    margin-bottom: 1rem;
  }

  .quest {
    display: flex;
  }

  button {
    margin: 5px auto;
    padding-top: 5px;
    padding-bottom: 5px;
    width: 150px;
  }

  .trueAnswer {
    background: green;
  }

  .falseAnswer {
    background: red;
  }
</style>