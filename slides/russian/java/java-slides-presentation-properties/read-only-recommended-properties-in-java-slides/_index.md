---
"description": "Узнайте, как включить свойства Read-Only Recommended в презентациях Java PowerPoint с помощью Aspose.Slides для Java. Следуйте нашему пошаговому руководству с примерами исходного кода для повышения безопасности презентаций."
"linktitle": "Рекомендуемые свойства только для чтения в слайдах Java"
"second_title": "API обработки Java PowerPoint Aspose.Slides"
"title": "Рекомендуемые свойства только для чтения в слайдах Java"
"url": "/ru/java/presentation-properties/read-only-recommended-properties-in-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Рекомендуемые свойства только для чтения в слайдах Java


## Введение в включение рекомендуемых свойств только для чтения в слайдах Java

В этом уроке мы рассмотрим, как включить свойства Read-Only Recommended для презентаций PowerPoint с помощью Aspose.Slides для Java. Свойства Read-Only Recommended могут быть полезны, когда вы хотите побудить пользователей просматривать презентацию без внесения каких-либо изменений. Эти свойства предполагают, что презентация должна быть открыта в режиме только для чтения. Мы предоставим вам пошаговое руководство вместе с исходным кодом Java для достижения этого.

## Предпосылки

Прежде чем начать, убедитесь, что в вашем проекте установлена библиотека Aspose.Slides for Java. Вы можете загрузить ее с [Сайт Aspose.Slides для Java](https://products.aspose.com/slides/java/).

## Шаг 1: Создайте новую презентацию PowerPoint

Начнем с создания новой презентации PowerPoint с помощью Aspose.Slides for Java. Если у вас уже есть презентация, вы можете пропустить этот шаг.

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
```

В приведенном выше коде мы определили путь к выходному файлу PowerPoint и создали новый объект презентации.

## Шаг 2: Включите рекомендуемое свойство «Только для чтения»

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

В этом фрагменте кода мы используем `getProtectionManager().setReadOnlyRecommended(true)` метод установки свойства «Рекомендуется только для чтения» на `true`. Это гарантирует, что когда кто-то откроет презентацию, ему будет предложено открыть ее в режиме только для чтения.

## Шаг 3: Сохраните презентацию

Наконец, мы сохраняем презентацию с включенным свойством «Рекомендуется только для чтения».

## Полный исходный код для рекомендуемых свойств только для чтения в слайдах Java

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

В этом уроке вы узнали, как включить свойство Read-Only Recommended для презентации PowerPoint с помощью Aspose.Slides for Java. Эта функция может быть полезна, когда вы хотите ограничить редактирование и побудить зрителей использовать презентацию в режиме только для чтения. Вы можете дополнительно повысить безопасность, установив пароль для презентации.

## Часто задаваемые вопросы

### Как отключить свойство «Рекомендуется только для чтения»?

Чтобы отключить свойство «Рекомендуется только для чтения», просто используйте следующий код:

```java
pres.getProtectionManager().setReadOnlyRecommended(false);
```

### Могу ли я установить пароль для презентации, доступной только для чтения?

Да, вы можете установить пароль для презентации «Только для чтения» с помощью Aspose.Slides для Java. Вы можете использовать `setPassword` метод установки пароля для презентации. Если установлен пароль, пользователям необходимо будет ввести его, чтобы открыть презентацию, даже в режиме только для чтения.

```java
pres.getProtectionManager().setPassword("YourPassword");
```

Не забудьте заменить `"YourPassword"` с желаемым паролем.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}