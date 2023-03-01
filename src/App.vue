<script setup>
import { ref } from 'vue'
import { getMails } from './composable/getMails.js'
import SingleMail from './components/SingleMail.vue'
const mails = ref(getMails())
// console.log(mails)
</script>
<template>
  <div class="w-full p-3">
    <div>
      <h1 class="flex justify-center text-2xl font-semibold">
        ~ Mailing List ~
      </h1>
    </div>
    <div class="w-full flex">
      <div class="flex w-2/12 justify-center tracking-widest font-semibold">
        Title
      </div>
      <div
        class="flex w-8/12 justify-self-center tracking-widest font-semibold"
      >
        Body
      </div>
      <div class="flex w-2/12 justify-center tracking-widest font-semibold">
        Keywords
      </div>
    </div>
    <div class="w-full flex" v-for="mail in mails" :key="mail.id">
      <SingleMail :mail="mail" />
    </div>
    <!-- <div class="grid grid-cols-8 gap-2">
      <div class="justify-self-center tracking-widest font-semibold">Title</div>
      <div class="col-span-6 justify-self-center tracking-widest font-semibold">
        Body
      </div>
      <div class="justify-self-center tracking-widest font-semibold">
        Keywords
      </div>
    </div>
    <div class="grid grid-cols-8 gap-2" v-for="mail in mails" :key="mail.id">
      <SingleMail
        :mail="mail"
        :layout="{ type: 'grid', colSpanNo: 2, colSpanValue: 6 }"
      />
    </div> -->
  </div>
</template>
<style scoped></style>
