# Strict Mode

Для включения strict mode, просто укажите `strict: true` при создании хранилища Vuex:

``` js
const store = new Vuex.Store({
  // ...
  strict: true
})
```

При использовании strict mode, любая попытка внесения изменений в состояние Vuex, кроме как через зарегистрированную мутацию, приведёт к появлению ошибки. Это позволяет быть уверенным, что все изменения с данными отслеживаются инструментами отладки.

### Разработка и production

**Не используйте strict mode в production-окружении!** Для определения некорректных операций, strict mode использует довольно "дорогие" операции глубокого наблюдения за деревом состояния приложения, поэтому удостоверьтесь что выключили этот режим перед выкладкой на production из соображений повышения производительности!

При использовании систем модульной сборки, это можно сделать так:

``` js
const store = new Vuex.Store({
  // ...
  strict: process.env.NODE_ENV !== 'production'
})
```
