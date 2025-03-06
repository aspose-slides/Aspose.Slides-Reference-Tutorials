---
title: Рекомендуемые свойства только для чтения в слайдах Java
linktitle: Рекомендуемые свойства только для чтения в слайдах Java
second_title: Aspose.Slides API обработки Java PowerPoint
description: Узнайте, как включить рекомендуемые свойства только для чтения в презентациях Java PowerPoint с помощью Aspose.Slides для Java. Следуйте нашему пошаговому руководству с примерами исходного кода для повышения безопасности презентаций.
weight: 17
url: /ru/java/presentation-properties/read-only-recommended-properties-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Введение в включение рекомендуемых свойств, доступных только для чтения, в слайдах Java

В этом уроке мы рассмотрим, как включить рекомендуемые свойства только для чтения для презентаций PowerPoint с помощью Aspose.Slides для Java. Рекомендуемые свойства только для чтения могут быть полезны, если вы хотите, чтобы пользователи просматривали презентацию без внесения каких-либо изменений. Эти свойства предполагают, что презентацию следует открывать в режиме только для чтения. Для этого мы предоставим вам пошаговое руководство вместе с исходным кодом Java.

## Предварительные условия

 Прежде чем мы начнем, убедитесь, что в вашем проекте установлена библиотека Aspose.Slides for Java. Вы можете скачать его с сайта[Веб-сайт Aspose.Slides для Java](https://products.aspose.com/slides/java/).

## Шаг 1. Создайте новую презентацию PowerPoint

Мы начнем с создания новой презентации PowerPoint с использованием Aspose.Slides для Java. Если у вас уже есть презентация, вы можете пропустить этот шаг.

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
```

В приведенном выше коде мы определили путь к выходному файлу PowerPoint и создали новый объект презентации.

## Шаг 2. Включите рекомендуемое свойство, доступное только для чтения.

Теперь давайте включим для презентации свойство «Рекомендуется только для чтения».

```java
try
{
    pres.getProtectionManager().setReadOnlyRecommended(true);
    pres.save(outPptxPath, SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

 В этом фрагменте кода мы используем`getProtectionManager().setReadOnlyRecommended(true)` метод, чтобы установить для свойства «Рекомендуется только для чтения» значение`true`. Это гарантирует, что когда кто-то откроет презентацию, ему будет предложено открыть ее в режиме только для чтения.

## Шаг 3. Сохраните презентацию

Наконец, мы сохраняем презентацию с включенным свойством «Рекомендуется только для чтения».

## Полный исходный код рекомендуемых свойств, доступных только для чтения, в слайдах Java

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
try
{
	pres.getProtectionManager().setReadOnlyRecommended(true);
	pres.save(outPptxPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Заключение

В этом руководстве вы узнали, как включить свойство «Рекомендуется только для чтения» для презентации PowerPoint с помощью Aspose.Slides для Java. Эта функция может быть полезна, если вы хотите ограничить редактирование и побудить зрителей использовать презентацию в режиме только для чтения. Вы можете еще больше повысить безопасность, установив пароль для презентации.

## Часто задаваемые вопросы

### Как отключить свойство «Рекомендуется только для чтения»?

Чтобы отключить свойство «Рекомендуется только для чтения», просто используйте следующий код:

```java
pres.getProtectionManager().setReadOnlyRecommended(false);
```

### Могу ли я установить пароль для презентации, рекомендованной только для чтения?

Да, вы можете установить пароль для презентации, рекомендованной только для чтения, с помощью Aspose.Slides для Java. Вы можете использовать`setPassword` метод установки пароля для презентации. Если установлен пароль, пользователям необходимо будет ввести его, чтобы открыть презентацию, даже в режиме только для чтения.

```java
pres.getProtectionManager().setPassword("YourPassword");
```

 Не забудьте заменить`"YourPassword"` с желаемым паролем.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
