---
title: Конвертировать формат PPT в формат PPTX
linktitle: Конвертировать формат PPT в формат PPTX
second_title: Aspose.Slides .NET API обработки PowerPoint
description: Узнайте, как легко конвертировать PPT в PPTX с помощью Aspose.Slides для .NET. Пошаговое руководство с примерами кода для плавного преобразования формата.
weight: 25
url: /ru/net/presentation-manipulation/convert-ppt-to-pptx-format/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Конвертировать формат PPT в формат PPTX


Если вам когда-либо приходилось конвертировать файлы PowerPoint из старого формата PPT в новый формат PPTX с помощью .NET, вы попали по адресу. В этом пошаговом руководстве мы покажем вам весь процесс с использованием API Aspose.Slides для .NET. С помощью этой мощной библиотеки вы сможете легко и просто выполнять такие преобразования. Давайте начнем!

## Предварительные условия

Прежде чем мы углубимся в код, убедитесь, что у вас настроено следующее:

- Visual Studio: убедитесь, что у вас установлена Visual Studio и готова к разработке .NET.
-  Aspose.Slides для .NET: Загрузите и установите библиотеку Aspose.Slides для .NET с сайта[здесь](https://releases.aspose.com/slides/net/).

## Настройка проекта

1. Создайте новый проект. Откройте Visual Studio и создайте новый проект C#.

2. Добавьте ссылку на Aspose.Slides. Щелкните правой кнопкой мыши свой проект в обозревателе решений, выберите «Управление пакетами NuGet» и найдите «Aspose.Slides». Установите пакет.

3. Импортируйте необходимые пространства имен:

```csharp
using Aspose.Slides;
```

## Преобразование PPT в PPTX

Теперь, когда наш проект настроен, давайте напишем код для преобразования файла PPT в PPTX.

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

string srcFileName = dataDir + "Conversion PPT to PPTX.ppt";
string destFileName = dataDir + "Conversion PPT to PPTX.pptx";

// Создайте экземпляр объекта Presentation, представляющего файл PPT.
Presentation pres = new Presentation(srcFileName);

//Сохранение презентации в формате PPTX.
pres.Save(outPath, SaveFormat.Pptx);
```

В этом фрагменте кода:

- `dataDir` следует заменить на путь к каталогу, в котором находится ваш файл PPT.
- `outPath` следует заменить каталогом, в котором вы хотите сохранить преобразованный файл PPTX.
- `srcFileName` — это имя вашего входного файла PPT.
- `destFileName` — желаемое имя выходного файла PPTX.

## Заключение

Поздравляем! Вы успешно преобразовали презентацию PowerPoint из формата PPT в формат PPTX с помощью API Aspose.Slides для .NET. Эта мощная библиотека упрощает подобные сложные задачи, делая процесс разработки .NET более плавным.

 Если вы еще этого не сделали,[скачать Aspose.Slides для .NET](https://releases.aspose.com/slides/net/) и изучить его возможности дальше.

 Дополнительные руководства и советы можно найти на нашем сайте[документация](https://reference.aspose.com/slides/net/).

## Часто задаваемые вопросы

### 1. Что такое Aspose.Slides для .NET?
Aspose.Slides for .NET — это библиотека .NET, которая позволяет разработчикам программно создавать, манипулировать и конвертировать презентации PowerPoint.

### 2. Могу ли я конвертировать другие форматы в PPTX с помощью Aspose.Slides for .NET?
Да, Aspose.Slides для .NET поддерживает различные форматы, включая PPT, PPTX, ODP и другие.

### 3. Можно ли использовать Aspose.Slides для .NET бесплатно?
 Нет, это коммерческая библиотека, но вы можете изучить[бесплатная пробная версия](https://releases.aspose.com/) оценить его особенности.

### 4. Поддерживаются ли Aspose.Slides для .NET какие-либо другие форматы документов?
Да, Aspose.Slides for .NET также поддерживает работу с документами Word, электронными таблицами Excel и другими форматами файлов.

### 5. Где я могу получить поддержку или задать вопросы об Aspose.Slides для .NET?
 Вы можете найти ответы на свои вопросы и обратиться за поддержкой в[Форумы Aspose.Slides](https://forum.aspose.com/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
