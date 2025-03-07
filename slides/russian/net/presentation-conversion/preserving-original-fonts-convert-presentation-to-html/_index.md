---
title: Сохранение оригинальных шрифтов — преобразование презентации в HTML
linktitle: Сохранение оригинальных шрифтов — преобразование презентации в HTML
second_title: Aspose.Slides .NET API обработки PowerPoint
description: Узнайте, как сохранить оригинальные шрифты при преобразовании презентаций в HTML с помощью Aspose.Slides для .NET. Обеспечьте единообразие шрифта и визуальное воздействие без особых усилий.
weight: 14
url: /ru/net/presentation-conversion/preserving-original-fonts-convert-presentation-to-html/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Сохранение оригинальных шрифтов — преобразование презентации в HTML


В этом подробном руководстве мы покажем вам процесс сохранения исходных шрифтов при преобразовании презентации в HTML с помощью Aspose.Slides для .NET. Мы предоставим вам необходимый исходный код C# и подробно объясним каждый шаг. К концу этого руководства вы сможете убедиться, что шрифты в преобразованном HTML-документе сохраняют соответствие исходному представлению.

## 1. Введение

При преобразовании презентаций PowerPoint в HTML крайне важно сохранить оригинальные шрифты, чтобы обеспечить визуальную согласованность вашего контента. Aspose.Slides для .NET предоставляет мощное решение для достижения этой цели. В этом уроке мы покажем вам, как сохранить исходные шрифты в процессе преобразования.

## 2. Предварительные условия

Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:

- Visual Studio установлена на вашем компьютере.
- В ваш проект добавлена библиотека Aspose.Slides for .NET.

## 3. Настройка вашего проекта

Для начала создайте новый проект в Visual Studio и добавьте библиотеку Aspose.Slides for .NET в качестве ссылки.

## 4. Загрузка презентации

Используйте следующий код для загрузки презентации PowerPoint:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation("input.pptx"))
{
    // Ваш код здесь
}
```

 Заменять`"Your Document Directory"` с путем к файлу презентации.

## 5. Исключение шрифтов по умолчанию

Чтобы исключить шрифты по умолчанию, такие как Calibri и Arial, используйте следующий код:

```csharp
string[] fontNameExcludeList = { "Calibri", "Arial" };
```

Вы можете настроить этот список по мере необходимости.

## 6. Встраивание всех шрифтов

Далее мы встроим все шрифты в HTML-документ. Это гарантирует сохранение исходных шрифтов. Используйте следующий код:

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);

HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(embedFontsController)
};
```

## 7. Сохранение в формате HTML

Теперь сохраните презентацию как HTML-документ со встроенными шрифтами:

```csharp
pres.Save("output.html", SaveFormat.Html, htmlOptionsEmbed);
```

 Заменять`"output.html"` с желаемым именем выходного файла.

## 8. Заключение

В этом уроке мы продемонстрировали, как сохранить оригинальные шрифты при преобразовании презентации PowerPoint в HTML с помощью Aspose.Slides для .NET. Выполнив эти шаги, вы можете быть уверены, что преобразованный HTML-документ сохранит визуальную целостность исходной презентации.

## 9. Часто задаваемые вопросы

### Вопрос 1. Могу ли я настроить список исключенных шрифтов?

 Да, ты можешь. Измените`fontNameExcludeList`массив для включения или исключения определенных шрифтов в соответствии с вашими требованиями.

### Вопрос 2. Что делать, если я не хочу встраивать все шрифты?

Если вы хотите встроить только определенные шрифты, вы можете соответствующим образом изменить код. Для получения более подробной информации обратитесь к документации Aspose.Slides for .NET.

### Вопрос 3. Существуют ли какие-либо лицензионные требования для использования Aspose.Slides для .NET?

Да, вам может потребоваться действующая лицензия для использования Aspose.Slides for .NET в ваших проектах. Информацию о лицензировании можно найти на веб-сайте Aspose.

### Вопрос 4. Могу ли я конвертировать другие форматы файлов в HTML с помощью Aspose.Slides для .NET?

Aspose.Slides for .NET в первую очередь ориентирован на презентации PowerPoint. Для преобразования других форматов файлов в HTML вам может потребоваться изучить другие продукты Aspose, адаптированные для этих форматов.

### Вопрос 5. Где я могу получить доступ к дополнительным ресурсам и поддержке?

 Дополнительную документацию, учебные пособия и поддержку можно найти на веб-сайте Aspose. Посещать[Документация Aspose.Slides для .NET](https://reference.aspose.com/slides/net/) для получения подробной информации.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
