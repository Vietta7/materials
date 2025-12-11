
## Шпаргалка ESLint для чистого кода

## Что проверяет

- **Именование**: camelCase (переменные/функции), PascalCase (классы), is/has* (boolean), ≥2 символа
    
- **TypeScript**: no any, явные return types, Record вместо {}, import type
    
- **Функции**: ≤30 строк, ≤3 параметра, вложенность ≤3
    
- **Код**: const по умолчанию, no console.log, no magic numbers , no nested ternary, скобки всегда

- **React**: named exports, key в map, no dangerouslySetInnerHTML, hooks rules, import order
    
- **Async**: обработка промисов, await в async
    
## Команды

|Linux/Mac|Windows (PowerShell/CMD)|Описание|
|---|---|---|
|`pnpm run lint`|`pnpm run lint`|Проверка|
|`pnpm run lint:fix`|`pnpm run lint:fix`|Автофикс|
|`pnpm run format`|`pnpm run format`|Форматирование|
|`pnpm run format:check`|`pnpm run format:check`|Проверка формата|
|`pnpm run check:dead-code`|`pnpm run check:dead-code`|Мертвый код|


**Linux/Mac:**

`cp eslint.config.js tsconfig.json .prettierrc.json package.json your-project/`
`cd your-project && pnpm install`
`pnpm run lint && pnpm run format:check`

**Windows (PowerShell):**

`Copy-Item eslint.config.js,tsconfig.json,.prettierrc.json,package.json your-project/`
`cd your-project`
`pnpm install`
`pnpm run lint && pnpm run format:check`

**Windows (CMD):**

`copy eslint.config.js tsconfig.json .prettierrc.json package.json your-project\`
`cd your-project`
`pnpm install`
`pnpm run lint && pnpm run format:check`

## Чек-лист
- [ ] camelCase/PascalCase  
- [ ] Нет any/object  
- [ ] ≤30 строк/функция  
- [ ] Named exports  
- [ ] Await везде  
- [ ] Нет magic values  
- [ ] pnpm run lint:fix
---

## Полезные ресурсы

- [TypeScript ESLint Rules](https://typescript-eslint.io/rules/)
    
- [Prettier Docs](https://prettier.io/docs/en/)
