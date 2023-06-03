<template>
  <section class="my-36" id="register">
    <div class="gap-y-14 md:grid-cols-2 grid ml-[1px]">
      <div class="flex flex-col gap-12">
        <h2 class="text-titleColor text-2xl font-bold">
          Ще маєте запитання?<br>
        Не соромтесь їх ставити.
        </h2>

        <div class="grid gap-y-8">
          <Info
            title="Телефон"
            icon="majesticons:phone-line"
            alt="telephone icon"
            text="+380992366838"
            link="tel:+380992366838"
          />

          <Info
            title="Пошта"
            icon="majesticons:mail-line"
            alt="E-mail icon"
            text="hello@smm.com"
            link="mailto:hello@smm.com"
          />
        </div>
      </div>

      <form
        @submit="handleFormData"
        method="post"
        action="https://sheetdb.io/api/v1/cbd9dtz2dqv4i"
      >
        <div class="grid gap-y-6 mb-6">
          <Input type="text" label="Ім'я" name="Ім'я" />
          <Input type="text" label="Прізвище" name="Прізвище" />
          <Input type="email" label="Email" name="email" />
          <Input type="tel" label="Номер телефону" name="Номер телефону" />

          <div class="relative h-28">
            <textarea
              name="питання"
              id="питання"
              placeholder=" "
              class="contractInput focus:labelUp"
            ></textarea>
            <label class="labelDown" for="питання">Запитання</label>
          </div>
        </div>

        <button class="buttonFirstColor" type="submit">
          Зареєструватись
          <i class="ri-arrow-right-up-line button__icon"></i>
        </button>
      </form>
    </div>
  </section>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import Info from '../molecules/Info.vue'
import Input from '../atoms/Input.vue'

export default defineComponent({
  components: { Info, Input },
  methods: {
    handleFormData(event: Event) {
      event.preventDefault()
      const form = document.querySelector('form')

      fetch(form!.action, {
        method: 'POST',
        body: new FormData(form!)
      })
        .then((response) => response.json())
        .then((html) => {
          if (html.created) {
            form!.reset()
            this.$notify({
              type: 'success',
              text: `${html.created} ви зареєструвались!`
            })
          } else {
            this.$notify({
              type: 'error',
              text: `ERRO: ${html.error}`
            })
          }
        })
    }
  }
})
</script>
