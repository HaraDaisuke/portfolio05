<template>
  <v-container fluid>
    <v-row justify="center">
      <v-col cols="12" sm="8" md="6">
        <v-card class="pa-5">
          <v-card-title class="text-h5 text-center">お問い合わせ</v-card-title>
          <v-form ref="form" v-model="valid">
            <v-text-field v-model="name" label="名前" :rules="nameRules" required></v-text-field>
            <v-text-field v-model="email" label="メールアドレス" :rules="emailRules" required></v-text-field>
            <v-textarea v-model="message" label="メッセージ" :rules="messageRules" required></v-textarea>
            <v-btn :disabled="!valid" color="primary" block @click="submitForm">送信</v-btn>
          </v-form>
          <v-alert v-if="submitted" type="success" class="mt-3">お問い合わせを送信しました！</v-alert>
          <v-alert v-if="error" type="error" class="mt-3">送信に失敗しました。再試行してください。</v-alert>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      valid: false,
      name: "",
      email: "",
      message: "",
      submitted: false,
      error: false,
      nameRules: [(v) => !!v || "名前を入力してください"],
      emailRules: [
        (v) => !!v || "メールアドレスを入力してください",
        (v) => /.+@.+\..+/.test(v) || "正しいメールアドレスを入力してください",
      ],
      messageRules: [(v) => !!v || "メッセージを入力してください"],
    };
  },
  methods: {
    submitForm() {
      if (this.$refs.form.validate()) {
        // 簡易的な送信処理（実際にはAPI通信などを実装）
        this.submitted = true;
        this.error = false;
        setTimeout(() => (this.submitted = false), 5000);
      } else {
        this.error = true;
      }
    },
  },
};
</script>

<style scoped>
.white-bg {
  background-color: #f5f5f5;
  color: black;
  min-height: 100vh;
  padding-top: 20px;
}
.v-card {
  max-width: 500px;
  background-color: white;
  color: black;
}
</style>

