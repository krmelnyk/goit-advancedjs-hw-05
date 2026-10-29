# goit-advancedjs-hw-05

Середовище TypeScript із компіляцією в JavaScript і source maps для налагодження у браузері.

## Встановлення та запуск

Потрібні Node.js 22.12+ і npm.

```sh
npm ci
npm run build
npm start
```

`npm start` автоматично компілює TypeScript і запускає `@web/dev-server`, який відкриває сторінку в браузері. Сторінка використовує скомпільований `dist/index.js`.

Для автоматичної компіляції під час редагування запусти в окремому терміналі:

```sh
npm run watch
```

Після змін онови сторінку. Перевірка типів без генерації файлів: `npm run typecheck`.

## Налаштування компілятора

У `tsconfig.json` задано `src` як каталог вихідного коду, `dist` як каталог результатів, `strict: true` для суворої перевірки типів і `noEmitOnError: true`, щоб не генерувати JavaScript із помилками типів.

`sourceMap: true` створює поруч із JavaScript файли `.js.map`. Каталоги `dist` і `node_modules` виключено з Git; залежності зафіксовано у `package-lock.json`.

## Налагодження у браузері

1. Виконай `npm run build` і `npm start`, відкрий сторінку.
2. Відкрий DevTools → Settings → Sources і перевір, що JavaScript source maps увімкнено.
3. У вкладці Sources знайди `src/index.ts` (за потреби через Ctrl+P / Cmd+P).
4. Постав breakpoint на рядку `concatenation(input.value, 'hello!')`.
5. Введи текст у поле й натисни `Concat!`: виконання зупиниться на відповідному рядку TypeScript. Перевір значення `input.value`.
