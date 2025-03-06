---
title: Установить резервный шрифт в Java PowerPoint
linktitle: Установить резервный шрифт в Java PowerPoint
second_title: Aspose.Slides API обработки Java PowerPoint
description: Узнайте, как установить резервные шрифты в Java PowerPoint с помощью Aspose.Slides для Java, чтобы обеспечить согласованное отображение текста.
weight: 16
url: /ru/java/java-powerpoint-text-font-customization/set-font-fallback-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Введение
В этом уроке мы углубимся в тонкости настройки резервных шрифтов в презентациях Java PowerPoint с использованием Aspose.Slides для Java. Резервные шрифты имеют решающее значение для обеспечения правильного отображения текста в ваших презентациях на разных устройствах и в различных операционных системах, даже если необходимые шрифты недоступны.
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующее:
- В вашей системе установлен Java Development Kit (JDK).
-  Aspose.Slides для библиотеки Java. Вы можете скачать его с[здесь](https://releases.aspose.com/slides/java/).
- Базовое понимание языка программирования Java.
- Интегрированная среда разработки (IDE), такая как IntelliJ IDEA или Eclipse.

## Импортировать пакеты
Сначала включите необходимые пакеты Aspose.Slides for Java в свой класс Java:
```java
import com.aspose.slides.FontFallBackRule;
import com.aspose.slides.IFontFallBackRule;
```
## Шаг 1. Инициализация резервных правил для шрифтов
Чтобы установить резервные шрифты, необходимо определить правила, определяющие диапазоны Юникода и соответствующие резервные шрифты. Вот как вы можете инициализировать эти правила:
```java
long startUnicodeIndex = 0x0B80;
long endUnicodeIndex = 0x0BFF;
IFontFallBackRule firstRule = new FontFallBackRule(startUnicodeIndex, endUnicodeIndex, "Vijaya");
IFontFallBackRule secondRule = new FontFallBackRule(0x3040, 0x309F, "MS Mincho, MS Gothic");
String[] fontNames = new String[]{"Segoe UI Emoji, Segoe UI Symbol", "Arial"};
IFontFallBackRule thirdRule = new FontFallBackRule(0x1F300, 0x1F64F, fontNames);
```
## Шаг 2. Примените резервные правила для шрифтов
Затем вы применяете эти правила к презентации или слайду, где необходимо установить резервные шрифты. Ниже приведен пример применения этих правил к слайду презентации PowerPoint:
```java
// Предполагая, что слайд — это ваш объект Slide.
slide.getFontsManager().setFontFallBackRules(new IFontFallBackRule[]{firstRule, secondRule, thirdRule});
```

## Заключение
Настройка резервных шрифтов в презентациях Java PowerPoint с использованием Aspose.Slides for Java необходима для обеспечения согласованного отображения текста в различных средах. Определив резервные правила, как показано в этом руководстве, вы можете обрабатывать ситуации, когда определенные шрифты недоступны, сохраняя целостность ваших презентаций.

## Часто задаваемые вопросы
### Что такое резервные шрифты в презентациях PowerPoint?
Резервные шрифты обеспечивают правильное отображение текста, заменяя доступные шрифты теми, которые не установлены.
### Как загрузить Aspose.Slides для Java?
 Вы можете скачать Aspose.Slides для Java с сайта[здесь](https://releases.aspose.com/slides/java/).
### Совместим ли Aspose.Slides for Java со всеми Java IDE?
Да, Aspose.Slides for Java совместим с популярными Java IDE, такими как IntelliJ IDEA и Eclipse.
### Могу ли я получить временные лицензии на продукты Aspose?
Да, временные лицензии на продукты Aspose можно получить на сайте[здесь](https://purchase.aspose.com/temporary-license/).
### Где я могу найти поддержку Aspose.Slides для Java?
 Для получения поддержки, связанной с Aspose.Slides для Java, посетите[Aspose форум](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
