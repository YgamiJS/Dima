---
author: YgamiJS
pubDatetime: 2023-04-23
title: React Query
postSlug: React Query
featured: true
draft: false
tags:
  - react query
ogImage: ""
description: React Query
---

# React Query

**React Query** - это мощный менеджер ансинхронного состояния , он предоставляет вам декларативные, всегда актуальные автоматически управляемые запросы и мутации, которые напрямую улучшают работу как разработчиков, так и пользователей.

## Он имеет ряд таких примуществ как:

- ### Декларативость и автоматизация

  **На этом логика выборки данных вручную закончена. Сообщите React Query, где взять ваши данные и насколько свежими они должны быть, а все остальное будет сделано автоматически. Он обрабатывает кэширование, фоновые обновления и устаревшие данные из коробки с нулевой конфигурацией.**

- ### Простоту и знакомость

  **Если вы знаете, как работать с промисами или асинхронностью/ожиданием, то вы уже знаете, как использовать React Query. Нет глобального состояния для управления, редукторов, систем нормализации или сложных конфигураций для понимания . Просто передайте функцию, которая разрешает ваши данные (или выдает ошибку), а остальное уже история.**

- ### Расширяемость

  **React Query настраивается для каждого экземпляра запроса наблюдателя с регуляторами и параметрами, подходящими для каждого варианта использования. Он поставляется со специальными инструментами разработки, API с бесконечной загрузкой и первоклассными инструментами изменения, которые упрощают обновление ваших данных . Не волнуйтесь, все заранее настроено на успех!**

## Установка

### npm

```bash
npm i @tanstack/react-query
```

### pnpm

```bash
pnpm add @tanstack/react-query
```

### yarn

```bash
yarn add @tanstack/react-query
```

## Основы

Базовый пример на react query:

```js
import {
  QueryClient,
  QueryClientProvider,
  useQuery,
} from "@tanstack/react-query";

const queryClient = new QueryClient();

export default function App() {
  return (
    <QueryClientProvider client={queryClient}>
      <Example />
    </QueryClientProvider>
  );
}

function Example() {
  const { isLoading, error, data } = useQuery({
    queryKey: ["repoData"],
    queryFn: () =>
      fetch("https://api.github.com/repos/tannerlinsley/react-query").then(
        res => res.json()
      ),
  });

  if (isLoading) return "Loading...";

  if (error) return "An error has occurred: " + error.message;

  return (
    <div>
      <h1>{data.name}</h1>
      <p>{data.description}</p>
      <strong>👀 {data.subscribers_count}</strong>{" "}
      <strong>✨ {data.stargazers_count}</strong>{" "}
      <strong>🍴 {data.forks_count}</strong>
    </div>
  );
}
```

В приведенном выше примере вы можете увидеть, как React Query в его самой простой и простой форме используется для получения статистики GitHub для самого проекта React Query GitHub:

**useQuery** - хук , которому мы передаем объект настроек с свойсвами queryKey - идификация запроса по которому будет осущиствлять кэширование и выбрарка данных , queryFn - функция запроса которая возвращеат promise (обещание) результат или ошибку.

Это был краткий обзор React Query , более подробно вы можете ознакомиться на его [сайте](https://tanstack.com/query/latest/docs/react/)
