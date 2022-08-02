<template>
  <p>
    Faça uma pergunta de sim/não:
    <input v-model="question" />
  </p>
  <p>{{ answer }}</p>
</template>

<script>
export default {
  data() {
    return {
      question: "",
      answer: "Sua resposta ficara aqui",
    };
  },
  watch: {
    question(newQuestion) {
      // se o campo de pergunta mudar essa função sera executada
      if (newQuestion.indexOf("?") > -1) {
        // se o ultimo caracter for ? dai vai executar a função abaixo
        this.getAnswer(); // ela faz um fatch a api e ela vai retornar a resposta
      }
    },
  },
  methods: {
    async getAnswer() {
      this.answer = "Pensando...";
      try {
        const res = await fetch("https://yesno.wtf/api");
        this.answer = (await res.json()).answer == "no" ? "não" : "sim";
      } catch (error) {
        this.answer = "Erro no servidor tente mais tarde. " + error;
      }
    },
  },
};
</script>

<style scoped></style>
