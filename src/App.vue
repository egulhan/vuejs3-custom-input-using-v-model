<template>
  <form @submit.prevent="submitForm">
    <div class="input-group">
      <label>How are you feeling?</label>
      <multiple-choice-input
          v-model="selectedFeelingIndex"
          :options="feelingOptions">
      </multiple-choice-input>
    </div>
    <div class="input-group">
      <button type="submit">Send</button>
    </div>
  </form>
</template>

<script>
import MultipleChoiceInput from "@/components/MultipleChoiceInput";

export default {
  name: "App",
  components: {MultipleChoiceInput},
  data() {
    return {
      selectedFeelingIndex: 0,
      feelingOptions: ['Awesome', 'So so', 'Sad'],
    };
  },
  methods: {
    submitForm() {
      alert(`You selected: ${this.feelingOptions[this.selectedFeelingIndex]}`);
    }
  },
}
</script>