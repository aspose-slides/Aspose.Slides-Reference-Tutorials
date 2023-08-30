---
title: Добавить гиперссылку на слайд
linktitle: Добавить гиперссылку на слайд
second_title: Aspose.Slides .NET API обработки PowerPoint
description: Узнайте, как добавлять гиперссылки к слайдам в PowerPoint с помощью Aspose.Slides для .NET. Дополните презентации интерактивным контентом.
type: docs
weight: 12
url: /ru/net/hyperlink-manipulation/add-hyperlink/
---

## Введение в Aspose.Slides для .NET

Aspose.Slides for .NET — это комплексная библиотека, которая позволяет разработчикам создавать, изменять и манипулировать презентациями PowerPoint, не полагаясь на Microsoft Office. Он предоставляет широкий спектр функций, включая добавление гиперссылок на слайдах и управление ими.

## Предварительные условия

Прежде чем начать, убедитесь, что у вас есть следующие предварительные условия:

- Visual Studio установлена в вашей системе.
-  Aspose.Slides для библиотеки .NET. Вы можете скачать его с[здесь](https://downloads.aspose.com/slides/net).

## Добавление гиперссылки к тексту на слайде

1. Создайте новый проект C# в Visual Studio.
2. Добавьте ссылку на DLL Aspose.Slides в свой проект.
3. Используйте следующий код, чтобы добавить гиперссылку к тексту на слайде:

```csharp
using Aspose.Slides;

// Загрузите презентацию
Presentation presentation = new Presentation("presentation.pptx");

// Доступ к слайду
ISlide slide = presentation.Slides[0];

// Доступ к текстовому полю
ITextFrame textFrame = slide.Shapes[0] as ITextFrame;

// Добавьте часть текста с гиперссылкой
textFrame.Paragraphs[0].Portions[0].Text = "Visit our website!";
textFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new HyperlinkInfo("https://www.example.com", HyperlinkAction.MouseClick);
```

## Добавление гиперссылки к фигуре на слайде

1. Выполните описанные выше шаги, чтобы создать новый проект C# и добавить ссылку на Aspose.Slides.
2. Используйте следующий код, чтобы добавить гиперссылку к фигуре на слайде:

```csharp
using Aspose.Slides;

// Загрузите презентацию
Presentation presentation = new Presentation("presentation.pptx");

// Доступ к слайду
ISlide slide = presentation.Slides[0];

// Доступ к фигуре
IShape shape = slide.Shapes[1];

// Добавьте гиперссылку в фигуру
shape.HyperlinkClick = new HyperlinkInfo("https://www.example.com", HyperlinkAction.MouseClick);
```

## Добавление гиперссылки на слайд

1. Выполните начальные шаги, чтобы настроить проект C# и использовать библиотеку Aspose.Slides.
2. Используйте следующий код, чтобы добавить гиперссылку на слайд:

```csharp
using Aspose.Slides;

// Загрузите презентацию
Presentation presentation = new Presentation("presentation.pptx");

// Доступ к слайду
ISlide slide = presentation.Slides[2];

// Добавьте гиперссылку на слайд
slide.HyperlinkClick = new HyperlinkInfo("https://www.example.com", HyperlinkAction.MouseClick);
```

## Добавление внешних гиперссылок

Помимо внутренних гиперссылок, вы также можете добавлять к слайдам внешние гиперссылки. Используйте тот же подход, что и выше, но укажите внешний URL-адрес в качестве цели гиперссылки.

## Изменение и удаление гиперссылок

Чтобы изменить существующую гиперссылку или удалить ее, вы можете получить доступ к свойствам гиперссылки соответствующего элемента слайда и внести необходимые изменения.

## Заключение

Добавление гиперссылок к слайдам с помощью Aspose.Slides for .NET — это простой процесс, который может значительно повысить интерактивность ваших презентаций. Хотите ли вы создать ссылку на внешние ресурсы или создать навигацию внутри слайдов, Aspose.Slides предоставляет инструменты, необходимые для эффективного решения этих задач.

## Часто задаваемые вопросы

### Как удалить гиперссылку из части текста?

 Чтобы удалить гиперссылку из части текста, вы можете просто установить`HyperlinkClick` собственность`null` за эту порцию.

### Могу ли я добавлять гиперссылки к фигурам, отличным от текстовых полей?

Да, вы можете добавлять гиперссылки к различным фигурам, включая изображения и пользовательские фигуры, с помощью`HyperlinkClick` свойство.

### Совместим ли Aspose.Slides с различными форматами PowerPoint?

Да, Aspose.Slides поддерживает различные форматы PowerPoint, включая PPTX, PPT и другие.

### Как я могу проверить гиперссылки в моей презентации?

Вы можете запустить презентацию в программе просмотра или редакторе PowerPoint, чтобы проверить функциональность гиперссылок.

### Где я могу скачать библиотеку Aspose.Slides для .NET?

 Вы можете скачать библиотеку Aspose.Slides для .NET с веб-сайта Aspose:[Загрузите Aspose.Slides для .NET](https://releases.aspose.com/slides/net).