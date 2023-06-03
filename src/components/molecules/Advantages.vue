<template>
  <section
    class="flex flex-col md:flex-row my-32 gap-10 text-center w-fit mx-auto"
  >
    <Card title="10 липня" text="Курс триває 2 місяці" />

    <Card title="7 000 грн/міс." text="14 000 грн при повній оплаті курсу" />

    <Card title="25 студентів" text="кожен студент отримує регулярний фідбек від кураторів" />
  </section>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import Card from '../atoms/Card.vue'

export default defineComponent({
  components: {
    Card
  }
})
</script>
