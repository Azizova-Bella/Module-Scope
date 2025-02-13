# Понимание области видимости в модулях
![image](https://github.com/user-attachments/assets/b3552914-6f08-4b03-87bb-cca56bce4bc9)
Этот файл предназначен для описания функциональности, установки и использования библиотеки Module Scope. Библиотека создана для управления областями видимости в модулях, предоставляя удобный интерфейс для работы с переменными, функциями и классами.
![image](https://github.com/user-attachments/assets/c2cd7690-4ade-4950-a61c-937c081be385)

## Возможности

- Управление областями видимости.
- Определение и изменение доступности переменных.
- Удобный API для работы с модулями.
- Поддержка как локальных, так и глобальных контекстов.
- Легкая интеграция с популярными фреймворками и инструментами.
- Возможность вложенных областей видимости.

#### Создание области видимости
```javascript

const scope = new ScopeManager();
scope.addVariable('x', 42);
console.log(scope.getVariable('x'))

// Добавление функции
scope.addFunction('hello', () => console.log("Hello, World"));
scope.callFunction('hello'); 
```

#### Работа с контекстами
```javascript
// Работа с контекстами
scope.enterContext('new_context');
scope.addVariable('y', 100);
console.log(scope.getVariable('y')); // Вывод: 100
scope.exitContext();
console.log(scope.getVariable('y')); // Ошибка: Переменная 'y' недоступна в текущем контексте

// Использование вложенных контекстов
scope.enterContext('nested_context');
scope.addVariable('z', 300);
console.log(scope.getVariable('z')); // Вывод: 300
scope.exitContext();
```

#### Расширенное использование

```javascript
// Работа с глобальным контекстом
scope.setGlobalVariable('greeting', 'Hello, World!');
console.log(scope.getGlobalVariable('greeting')); // Вывод: Hello, World!

scope.addVariable('a', 1);
scope.addVariable('b', 2);
console.log(scope.listVariables()); // Вывод: ['a', 'b']

console.log(scope.hasVariable('a')); // Вывод: true
console.log(scope.hasVariable('c')); // Вывод: false
```




