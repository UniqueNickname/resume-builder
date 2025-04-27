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
            <p class="text-black text-opacity-50">Shkulev Holding (Интернет технологии)</p>
            <small class="text-black text-opacity-50">март 2022 - настоящее время</small>
            <div class="pl-4 space-y-4">
              <p class="pr-20">
                Компания занимается разработкой и поддержкой более 80 региональных новостных сайтов (ГП) и более 20 тематических порталов (ТЭП), включая NGS, E1, Fontanka, maxim.ru, psychologies.ru и woman.ru;
              </p>
              <div class="space-y-1">
                <p class="pr-24">
                  Поработал в разных командах над большим спектром задач:
                </p>
                <ul class="space-y-1">
                  <li class="pr-24">
                    - В составе UX Team участвовал в редизайне главной страницы и ключевых блоков (левой и правой колонок) в едином монорепозитории с конфигурируемой структурой под нужды городских порталов, используя Vue 2, Vuex и принципы Clean Architecture;
                  </li>
                  <li class="pr-24">
                    - В Core Team, будучи одним из двух фронтенд-разработчиков, занимался разработкой страницы статьи с множеством контентных блоков и внедрил большую часть аналитики Яндекс Метрики; участвовал в создании единого монорепозитория для городских и тематических порталов на основе архитектуры FSD;
                  </li>
                  <li class="pr-24">
                    - В Content Team расширил админ-панель для журналистов и редакторов: реализовал новые инструменты для редактора статей и полностью переписал систему авторизации;
                  </li>
                  <li class="pr-24">
                    - В Monetization Team полностью переписал существующий редактор рекламных конфигураций в админке на обновлённый стек технологий (миграция с Vue 2 и Vuex на Vue 3 и Pinia) и расширил набор утилит для упрощённой работы с формами;
                  </li>
                  <li class="pr-24">
                    - В составе Pogonline Team, будучи единственным фронтенд-разработчиком, поддерживаю существующий репозиторий проекта pogovorim.online на React.js и Next.js, одновременно ведётся переписывание всего проекта по новым макетам на Vue 3
                  </li>
                </ul>
              </div>
            </div>
          </div>
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
                Кварк - аутсорс компания.
              </p>
              <work-list title="Обязанности" :options="tasksKvark" />
            </div>
          </div>
        </div>
      </div>
      <div class="flex items-center justify-start space-x-4" style="margin-top: 120px;">
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
'JavaScript (ES6+)',
  'TypeScript',
  'HTML5 & CSS3 (SCSS/PostCSS, Tailwind CSS)',
  'Vue.js (2, 3) / Nuxt.js (2, 3)',
  'State Management: Vuex, Pinia',
  'React.js / Next.js',
  'Build Tools: Vite, Webpack',
  'Testing: Jest, Vitest, Testing Library',
  'Version Control: Git, GitHub',
  'Analytics: Yandex.Metrika',
  'API: REST, GraphQL',
  'Architecture & Patterns: Clean Architecture, FSD',
  'Docker, CI/CD',
  'Documentation: Histoire',
];

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
  'Разработка medzona.com, внесение новых фич, настройка мультиязычности',
  'Оперативно погружался в чужие кодовые базы для анализа и устранения критических багов, обеспечивая стабильность и качество релизов.',
]

const university = {
  'Факультет': 'Информационных технологий и компьютерных систем (ФИТиКС)',
  'Специальность': 'Информационные системы и технологии (ИСТ)',
}

const about = {
  'Занятия в свободное время': 'Регулярно занимаюсь фитнесом для поддержания энергии и увлекаюсь видеоиграми',
  'Личные качества': [
    'Ответственность и самодисциплина — полностью курирую фронтенд-часть проекта, принимая решения от архитектуры до деталей UI',
    'Проактивность — генерирую и внедряю идеи по улучшению интерфейсов и пользовательского опыта',
    'Гибкость и скорость погружения в задачу — часто приходилось работать над разными проектами на разных стэках, благодаря чему научился быстро осваивать новые кодовые базы и контексты и сразу эффективно в них работать.'
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
