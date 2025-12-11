
## Шпаргалка TypeScript Best Practices

## 1. Типизация

- **Запрет any** -включает строгий режим:
    
    json
    
    `"strict": true, "noImplicitAny": true, "strictNullChecks": true`
    
    ESLint:
    
    `'@typescript-eslint/no-explicit-any': 'error'`
    
- **unknown вместо any** -требует проверки типа.
    
- **Не использовать {} и object** - заменяй на `Record<string, T>` или интерфейсы.
    
- **Явные типы возврата** - всегда указывай `(): Type` или `(): Promise<Type>`.
    

## 2. type vs interface

- **type** -для объединений, пересечений, неизменяемых структур.
    
- **interface** -если нужно расширять (`extends`) или пользоваться декларативным объединением.

## 3. enum vs const

- **enum** -избегай (генерирует JS-код).
    
- **const enum** -можно, удаляется из JS.
    
- **as const** -предпочтителен
    
    `const STATUS = { OK: 'ok', FAIL: 'fail' } as const; type Status = (typeof STATUS)[keyof typeof STATUS];`
    

## 4. Type Guards / Assertions

- `as`  просто уверяет TS, не проверяет.
    
- **Type Guards**:
    
    - `typeof` для примитивов
        
    - `instanceof` для классов
        
    - `is`-функции для своих типов:
        
        `const isUser = (val: unknown): val is User => typeof val === 'object' && val !== null;`
        

## 5. Константы и Magic Values

- Числа и строки выноси в константы
    
    `const MAX_USERS = 10; const ROUTES = { HOME: '/', ABOUT: '/about' } as const;`
    
- Преимущества: меньше ошибок, автодополнение, масштабируемость.
    

## 6. Чек-лист

- [ ] Нет any  
- [ ] Есть строгие правила в ESLint  
- [ ] Используется `unknown`  
- [ ]  Константы вместо литералов  
- [ ] `as const` вместо `enum`  
- [ ] Типы и интерфейсы выбраны осознанно  
- [ ] Type Guards вместо `as`
---

## Полезные ресурсы

- [Официальная документация TypeScript](https://www.typescriptlang.org/docs/)
    
- [TypeScript Deep Dive (Basarat)](https://basarat.gitbook.io/typescript/)
    

