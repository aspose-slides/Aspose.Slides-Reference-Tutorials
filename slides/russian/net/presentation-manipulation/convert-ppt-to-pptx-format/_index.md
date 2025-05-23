---
"description": "Узнайте, как легко преобразовать PPT в PPTX с помощью Aspose.Slides для .NET. Пошаговое руководство с примерами кода для бесшовного преобразования формата."
"linktitle": "Конвертировать формат PPT в PPTX"
"second_title": "API обработки PowerPoint Aspose.Slides .NET"
"title": "Конвертировать формат PPT в PPTX"
"url": "/ru/net/presentation-manipulation/convert-ppt-to-pptx-format/"
"weight": 25
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Конвертировать формат PPT в PPTX


Если вам когда-либо требовалось преобразовать файлы PowerPoint из старого формата PPT в новый формат PPTX с помощью .NET, вы попали по адресу. В этом пошаговом руководстве мы проведем вас через процесс с использованием API Aspose.Slides для .NET. С этой мощной библиотекой вы сможете без усилий справляться с такими преобразованиями с легкостью. Давайте начнем!

## Предпосылки

Прежде чем погрузиться в код, убедитесь, что у вас настроено следующее:

- Visual Studio: убедитесь, что у вас установлена Visual Studio и она готова к разработке .NET.
- Aspose.Slides для .NET: Загрузите и установите библиотеку Aspose.Slides для .NET с сайта [здесь](https://releases.aspose.com/slides/net/).

## Настройка проекта

1. Создайте новый проект: откройте Visual Studio и создайте новый проект C#.

2. Добавьте ссылку на Aspose.Slides: щелкните правой кнопкой мыши свой проект в обозревателе решений, выберите «Управление пакетами NuGet» и найдите «Aspose.Slides». Установите пакет.

3. Импорт требуемых пространств имен:

```csharp
using Aspose.Slides;
```

## Конвертация PPT в PPTX

Теперь, когда наш проект готов, давайте напишем код для преобразования файла PPT в PPTX.

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

string srcFileName = dataDir + "Conversion PPT to PPTX.ppt";
string destFileName = dataDir + "Conversion PPT to PPTX.pptx";

// Создать объект Presentation, представляющий файл PPT.
Presentation pres = new Presentation(srcFileName);

// Сохранение презентации в формате PPTX
pres.Save(outPath, SaveFormat.Pptx);
```

В этом фрагменте кода:

- `dataDir` следует заменить на путь к каталогу, где находится ваш файл PPT.
- `outPath` следует заменить на каталог, в котором вы хотите сохранить преобразованный файл PPTX.
- `srcFileName` — это имя вашего входного файла PPT.
- `destFileName` желаемое имя для выходного файла PPTX.

## Заключение

Поздравляем! Вы успешно преобразовали презентацию PowerPoint из формата PPT в PPTX с помощью API Aspose.Slides для .NET. Эта мощная библиотека упрощает сложные задачи, подобные этой, делая процесс разработки .NET более плавным.

Если вы еще этого не сделали, [скачать Aspose.Slides для .NET](https://releases.aspose.com/slides/net/) и изучить его возможности более подробно.

Для получения дополнительных руководств и советов посетите наш [документация](https://reference.aspose.com/slides/net/).

## Часто задаваемые вопросы

### 1. Что такое Aspose.Slides для .NET?
Aspose.Slides для .NET — это библиотека .NET, которая позволяет разработчикам программно создавать, изменять и конвертировать презентации PowerPoint.

### 2. Можно ли конвертировать другие форматы в PPTX с помощью Aspose.Slides для .NET?
Да, Aspose.Slides для .NET поддерживает различные форматы, включая PPT, PPTX, ODP и другие.

### 3. Является ли использование Aspose.Slides для .NET бесплатным?
Нет, это коммерческая библиотека, но вы можете изучить [бесплатная пробная версия](https://releases.aspose.com/) оценить его особенности.

### 4. Поддерживаются ли Aspose.Slides для .NET какие-либо другие форматы документов?
Да, Aspose.Slides для .NET также поддерживает работу с документами Word, электронными таблицами Excel и другими форматами файлов.

### 5. Где я могу получить поддержку или задать вопросы по Aspose.Slides для .NET?
Вы можете найти ответы на свои вопросы и обратиться за поддержкой в [Форумы Aspose.Slides](https://forum.aspose.com/).



{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}