<template>
  <div id="core" class="grid grid-cols-4 gap-5 mx-auto text-lg bg-white base-container">
    <div class="col-span-4 h-[0px]">
      <div class="block h-8 mt-4 text-center">
        <h1 class="text-2xl font-bold uppercase">Кочура Иван Александрович</h1>
      </div>
      <div class="flex items-center justify-center mx-auto">
        <div class="flex items-center justify-between w-64 text-center">
          <p class="text-opacity-50">Front-end разработчик</p>
          <MapMarker />
          <p class="text-opacity-50">Омск</p>
        </div>
      </div>
    </div>
    <div class="col-span-1 mt-0 space-y-10 text-center">
      <div class="flex items-center justify-center h-[360px] pr-2 pl-4">
        <img :src="photo" alt="">
      </div>
      <left-block title="Контакты" :options="contacts" />
      <left-block title="Навыки" :options="skills" />
    </div>
    <div class="col-span-3 mt-20 space-y-4">
      <div class="">
        <div class="flex items-center justify-start space-x-4">
          <account />
          <h2 class="font-bold uppercase">Личная информация</h2>
        </div>
        <div class="border-l-2 border-gray-500 pl-6 ml-[7px] mt-2">
          <named-list :options="personal" />
        </div>
      </div>
      <div class="">
        <div class="flex items-center justify-start space-x-4">
          <briefcase />
          <h2 class="font-bold uppercase">Опыт работы</h2>
        </div>
        <div class="border-l-2 border-gray-500 pl-6 ml-[7px] mt-2 space-y-4">
          <div>
            <h3 class="text-xl font-bold">Front-end разработчик</h3>
            <p class="text-black text-opacity-50">WineStyle</p>
            <small class="text-black text-opacity-50">февраль 2022 - март 2022</small>
            <div class="pl-4 space-y-4">
              <p class="pr-20">
                Компания WineStyle занимается продажей элитных вин и прочих товаров.
                Мы командой разрабатывали новый интернет магазин с нуля.
                Проект на Nuxt 3 с postcss.
              </p>
              <work-list
                title="В основном разрабатывал библиотеку компонентов в соответствии с Atomic Design"
                :options="tasksWineStyle"
              />
              <!-- <p>
                Для каждого фильтра генерируется отдельная страница (e.g. /wine/red/france)
              </p>
              <p>
                Реализовал функционал для рендеринга в HTML при запросе данных для фильтров на стороне сервера всех ссылок для всех фильтров, чтоб скормить их поисковым ботам.
              </p>
              <p>
                При этом на стороне клиента произойдёт рендер только 5 ссылок в каждой категории. Остальные доступны только после нажатия на "Показать все".
              </p> -->
            </div>
          </div>
          <div>
            <h3 class="text-xl font-bold">Front-end разработчик</h3>
            <p class="text-black text-opacity-50">Спички</p>
            <small class="text-black text-opacity-50">март 2021 - ноябрь 2021</small>
            <div class="pl-4 space-y-4">
              <p class="pr-20">
                Спички - стартап по генерации озвучки для статей. Работал
                на проекте Retell.cc. Владельцы новостных сайтов подключают
                их к нашей системе, наш сервер парсит RSS и генерирует озвучку.
                Пользователи могут подключить к своим сайтам интеграционные
                скрипты, которые добавят плеер. Плеер служит для воспроизведения
                сгенерированных статей и сбора статистики.
              </p>
              <work-list title="Весь front-end разрабатывался лично мной" :options="tasksSpeechki" />
            </div>
          </div>
          <div>
            <h3 class="text-xl font-bold">Front-end разработчик</h3>
            <p class="text-black text-opacity-50">Кварк</p>
            <small class="text-black text-opacity-50">июнь 2020 - март 2021</small>
            <div class="pl-4 space-y-4">
              <p class="pr-24">
                Кварк - аутсорс компания. В основном работал на проекте medzona.com.
              </p>
              <work-list title="Обязанности" :options="tasksKvark" />
            </div>
          </div>
        </div>
      </div>
      <div class="flex items-center justify-start space-x-4">
        <school />
        <h2 class="font-bold uppercase">Образование</h2>
      </div>
      <div class="border-l-2 border-gray-500 pl-6 ml-[7px] mt-2 space-y-4">
        <h3 class="font-bold">Омский государственный университет</h3>
        <named-list :options="university" />
      </div>
      <div class="flex items-center justify-start space-x-4">
        <information />
        <h2 class="font-bold uppercase">Дополнительная информация</h2>
      </div>
      <div class="border-l-2 border-gray-500 pl-6 ml-[7px] mt-2 space-y-4">
        <named-list :options="about" />
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import MapMarker from 'vue-material-design-icons/MapMarker.vue'
import Account from 'vue-material-design-icons/Account.vue'
import Briefcase from 'vue-material-design-icons/Briefcase.vue'
import School from 'vue-material-design-icons/School.vue'
import Information from 'vue-material-design-icons/Information.vue'
import LeftBlock from './components/left-block.vue'
import WorkList from './components/work-list.vue'
import NamedList from './components/named-list.vue'
import photo from './assets/img/photo2.png'

const contacts = [
  '+79136745378',
  'dr.art-47@yandex.ru',
  'https://github.com/ UniqueNickname/',
  'Telegram - @uniquenickname13',
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

const tasksWineStyle = [
  'Множество простых компонентов',
  'Карусель. Компонент в slot принимает любое количество элементов, но внутри отрендерится только определённое количество, указанное в props. При пролистывании элементов вправо рендерятся отсутствующие элементы.',
  'Карточка товара. Компонент бывает в двух вариантах и двух размерах. При переключении вида (grid, list) или изменении размера экрана не меняется HTML. При этом элементы карточки меняются местами. Реализовано с помощью css grid.'
]

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

const university = {
  'Факультет': 'Информационных технологий и компьютерных систем (ФИТиКС)',
  'Специальность': 'Информационные системы и технологии (ИСТ)',
}

const about = {
  'Занятия в свободное время': 'Фитнес, видеоигры',
  'Личные качества': [
    'Отсутствие вредных привычек',
    'Самостоятельность - т.к. в компании Спички весь front-end на мне, многие решения принимались лично мной',
    'Инициативность - предлагал множество решений по улучшению UI и UX',
    'Быстрая обучаемость - часто приходилось переключаться между технологиями. Уже поработал и с vue 3, писал плагин для webpack с поддержкой v4 и v5, быстро изучил svelte, писал библиотеки для npm, плагины для vue и react'
  ],
}
</script>

<style lang="scss">
.base-container {
  $part_size: 2;
  width: calc(2480px / $part_size);
  height: calc(3508px / $part_size);
}
</style>
