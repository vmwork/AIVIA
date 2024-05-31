<template>
  <div class="">
    <v-card class="mx-auto my-8" elevation="16" max-width="800">
      <v-card-item>
        <v-card-title> Login</v-card-title>
      </v-card-item>

      <v-card-text>
        <v-sheet class="mx-auto" width="300">
          <v-form @submit.prevent>
            <v-text-field
              v-model="email"
              :rules="emailRules"
              label="Email"
            ></v-text-field>
            <v-text-field
              v-model="password"
              :rules="passwordRules"
              label="Password"
            ></v-text-field>
            <v-btn class="mt-2 mb-8" type="submit" @click="submit" block
              >Submit</v-btn
            >
          </v-form>
        </v-sheet>
      </v-card-text>
    </v-card>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";
import { useVuelidate } from "@vuelidate/core";
import { required } from "@vuelidate/validators";
import { useRouter } from "vue-router";

const router = useRouter();

const v$ = useVuelidate();

const email = ref("");
const password = ref("");

const emailRules = ref([""]);
const passwordRules = ref([""]);

const validations = () => {
  return {
    email: { required },
    password: { required },
  };
};

const submit = () => {
  if (!email.value) {
    emailRules.value = ["Input Email"];
  } else if (!password.value) {
    passwordRules.value = ["Input password"];
  } else {
    passwordRules.value = [""];
    emailRules.value = [""];
    router.push("/game");
  }
};
</script>
