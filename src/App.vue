<template>
<div class="bg-gray-300 py-10">
  <div class="base-container mx-auto bg-white grid grid-cols-3 gap-5">
    <div class="col-span-3 h-[456px]">
      <div class="flex items-center justify-center h-[400px]">
        <div class="mt-4 overflow-hidden w-[300px] h-[300px] bg-[url(photo.jpg)] rounded-lg" style="background-position: 25% 12%; background-size: 222%;" />
      </div>
      <div class="text-center block h-8">
        <h1 class="uppercase font-bold text-2xl">Кочура Иван Александрович</h1>
      </div>
      <div class="flex items-center justify-center mx-auto">
        <div class="w-64 text-center flex items-center justify-between">
          <p class="text-opacity-50">Front-end разработчик</p>
          <MapMarker />
          <p class="text-opacity-50">Омск</p>
        </div>
      </div>
    </div>
    <div class="col-span-1 text-center space-y-10">
      <left-block title="Контакты" :options="contacts" />
      <left-block title="Навыки" :options="skills" />
    </div>
    <div class="col-span-2 space-y-4">
      <div class="">
        <div class="flex items-center justify-start space-x-4">
          <account />
          <h2 class="uppercase font-bold">Личная информация</h2>
        </div>
        <div class="border-l-2 border-gray-500 pl-6 ml-[7px] mt-2">
          <ul class="space-y-2">
            <li v-for="[key, value] in Object.entries(personal)" :key="key">
              <span class="text-opacity-50 text-black mr-2">{{ key }}:</span>
              <span>{{ value }}</span>
            </li>
          </ul>
        </div>
      </div>
      <div class="">
        <div class="flex items-center justify-start space-x-4">
          <briefcase />
          <h2 class="uppercase font-bold">Опыт работы</h2>
        </div>
        <div class="border-l-2 border-gray-500 pl-6 ml-[7px] mt-2 space-y-4">
          <div>
            <h3 class="font-bold text-xl">Front-end разработчик</h3>
            <p class="text-opacity-50 text-black">Спички</p>
            <small class="text-opacity-50 text-black">март 2021 - ноябрь 2021</small>
            <div class="pl-4 space-y-4">
              <p class="pr-24">
                Спички - стартап по генерации озвучки для статей. Работал
                на проекте Retell.cc. Владельцы новостных сайтов подключают
                их к нашей системе, наш сервер парсит RSS и генерирует озвучку.
                Пользователи могут подключить к своим сайтам интеграционные
                скрипты, которые добавят плеер. Плеер служит для воспроизведения
                сгенерированных статей и сбора статистики.
              </p>
              <work-list title="Весь front-end разрабатывается лично мной" :options="tasksSpeechki" />
            </div>
          </div>
          <div>
            <h3 class="font-bold text-xl">Front-end разработчик</h3>
            <p class="text-opacity-50 text-black">Кварк</p>
            <small class="text-opacity-50 text-black">июнь 2020 - март 2021</small>
            <div class="pl-4 space-y-4">
              <p class="pr-24">
                Кварк - аутсорс компания. В основном работал на проекте medzona.com.
              </p>
              <work-list title="Обязанности" :options="tasksKvark" />
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>
</template>

<script setup lang="ts">
import MapMarker from 'vue-material-design-icons/MapMarker.vue'
import Account from 'vue-material-design-icons/Account.vue'
import Briefcase from 'vue-material-design-icons/Briefcase.vue'
import LeftBlock from './components/left-block.vue'
import WorkList from './components/work-list.vue'

const contacts = [
  '+79136745378',
  'dr.art-47@yandex.ru',
  'https://github.com/UniqueNickname/'
]

const skills = [
  'JavaScript',
  'TypeScrips',
  'Vuejs',
  'Nuxtjs',
  'Vite',
  'Webpack',
  'Svelte',
  'Jest'
]

const personal = {
  'Гражданство': 'Российская Федерация',
  'Образование': 'Высшее неполное',
  'Дата рождения': '1 августа 1999',
}

const tasksSpeechki = [
  'интерфейс админ панели',
  'виджеты на svelte и vue 3',
  'скрипты для интеграции виджетов на сайты пользователей',
  'интеграция с CMS Ghost',
  'кастомный SSR для проекта на основе vite',
  'плагины с виджетами для vue и react',
  'тесты для бизнес-логики и vue компонентов',
]

const tasksKvark = [
  'разработка пользовательского интерфейса в команде',
  'внесение исправлений в проекты, на которых ранее не работал (меня перекидывали на чужие проекты починить баги и нужно было крайне быстро освоиться на незнакомом проекте)',
]
</script>

<style lang="scss">
.base-container {
  $part_size: 2;
  width: calc(2480px / $part_size);
  height: calc(3508px / $part_size);
}
</style>
