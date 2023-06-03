<template>
  <main class="mx-5 xs:mx-14 lg:!mx-auto lg:max-w-5xl">
    <Section
      id="product"
      title="SMM: від стратегії до реклами"
      text="Курс для SMM менеджерів-початківців і тих, хто хоче перейти у сферу. За два місяці студенти розберуться в принципах і механіці соцмереж, щоб формувати та втілювати SMM стратегію бренду."
      :imgSrc="feedImg"
      alt="SMM"
    />

    <Advantages />
    <Testimonial />

    <Section
      title="Про курс"
      text="За два місяці студенти навчаться працювати в основних соціальних мережах (Facebook та Instagram), оцінювати ефективність своєї роботи, створювати комунікаційну стратегію і зрозуміють, що може робити бренд у мережі."
      :imgSrc="coursesImg"
      alt="About"
      reverse
    />

    <Contract />
  </main>
</template>

<script setup lang="ts">
//Images import:
import feedImg from '../../assets/img/app/feed.png'
import coursesImg from '../../assets/img/app/courses.png'
//Components import:
import Section from '../organisms/Section.vue'
import Advantages from '../molecules/Advantages.vue'
import Testimonial from '../organisms/Testimonial.vue'
import Contract from '../organisms/Contract.vue'
</script>
