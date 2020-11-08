# parcel-init-deploy-tutorial

## Мастерская: деплой билда от Parcel на GitHub Pages

1. Getting Started Parcel docs/   https://parceljs.org/  
2. Устанавливаем Parcel   `npm install parcel-bundler --save -dev`
3. Инициализируем проект `npm init` (автоматеически создадуться файлы package.json, package-lock.json),  `npm init -y`  - автоматическое заполнение данных проекта
4. Добавить скипта `dev, build`. И скрипты `deploy, predeploy` для автоматического деплоя на GitHub : 
   `"scripts": {
   "dev": "parcel src/index.html",
   "build": "parcel build src/index.html --public-url /(your-repository-name)/",
   "deploy": "gh-pages -d dist",
   "predeploy": "npm run build"
   }`
  
5. Редактрируем в package.json поле `"homepage": "https://ваше_имя.github.io/имя_репозитория"`
6. Устанавливаем пакет [`npm install gh-pages`] (https://www.npmjs.com/package/gh-pages) 

5. Создать 2 файла: index.html  и index.js. Подключить index.js в html как точку входа (entry file) в конце тега <body>
   `<html>
   <body>
      
     <script src="./index.js"></script>
   </body>
   </html>`
   
6. Добавить полезный плагин  `npm install parcel-plugin-nuke-dist --save-dev`, к/й очищает папку dist перед каждой новой сборкой npm run build или npm run deploy
7. Начало разработки  npm run dev,  Запуск в продакшин -  npm run build
   -  Плагин для SASS - `npm install -D sass`

Deploy Tutorial
1. Редактируем скрипт build и добавляем `--public-url /имя_репозитория/`
2. Редактрируем в package.json поле `"homepage": "https://ваше_имя.github.io/имя_репозитория"`
3. Устанавливаем пакет [`npm install gh-pages`](https://www.npmjs.com/package/gh-pages)
4. Добавляем npm-скрипты
   1. `"deploy": "gh-pages -d dist"`
   2. `"predeploy": "npm run build"`
