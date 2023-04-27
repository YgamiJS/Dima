---
author: YgamiJS
pubDatetime: 2023-04-27
title: React Native
postSlug: React Native
featured: true
draft: false
tags:
  - react native
ogImage: ""
description: React Native
---

# React Native

> Learn once, write anywhere.

**React Native** - это кроссплатформенный фреймворк с открытым исходным кодом для разработки нативных мобильных и настольных приложений на JavaScript и TypeScript, созданный Facebook. Поддерживаются различные платформы такие как: IOS , Android , Web , Windows , macOS , tvOS. Для рендеринга он использует библиотеку React.

## Архитектура

React Native использует **JSI** - это интерфейс , который позволяет объекту JavaScript содержать ссылку на C++ и наоборот.
Как только объект имеет ссылку на другой объект, он может напрямую вызывать методы для него. Так, например, объект C++ теперь может запрашивать у объекта JavaScript выполнение метода в мире JavaScript и наоборот.

## Базовый пример

```js
import React from "react";
import { Text, View } from "react-native";

const YourApp = () => {
  return (
    <View
      style={{
        flex: 1,
        justifyContent: "center",
        alignItems: "center",
      }}
    >
      <Text>Try editing me! 🎉</Text>
    </View>
  );
};

export default YourApp;
```

В этом примере используют компоненты `View` и `Text`. **View** cамый фундаментальный компонент для создания пользовательского интерфейса ,непосредственно с эквивалентом нативного представления на любой платформе, на которой работает React Native , **Text** это компонент для отображение текста.

Это был краткий обзор кроссплатформенного фреймворка React Native , более подробно вы можете ознакомиться на его [сайте](https://reactnative.dev/)
