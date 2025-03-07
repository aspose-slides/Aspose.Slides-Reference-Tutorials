---
title: Связывание видео через элемент управления ActiveX в PowerPoint
linktitle: Связывание видео через элемент управления ActiveX
second_title: Aspose.Slides .NET API обработки PowerPoint
description: Узнайте, как связать видео со слайдами PowerPoint с помощью Aspose.Slides для .NET. Это пошаговое руководство включает исходный код и советы по созданию интерактивных и интересных презентаций со связанными видео.
weight: 12
url: /ru/net/slide-view-and-layout-manipulation/linking-video-activex-control/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Связывание видео через элемент управления ActiveX в PowerPoint

Связывание видео через элемент управления ActiveX в презентации с использованием Aspose.Slides для .NET

В Aspose.Slides for .NET вы можете программно связать видео со слайдом презентации с помощью элемента управления ActiveX. Это позволяет создавать интерактивные презентации, в которых видеоконтент можно воспроизводить прямо на слайде. В этом пошаговом руководстве мы покажем вам процесс привязки видео к слайду презентации с помощью Aspose.Slides для .NET.

## Предпосылки:
- Visual Studio (или любая другая среда разработки .NET)
-  Aspose.Slides для библиотеки .NET. Вы можете скачать его с[здесь](https://releases.aspose.com/slides/net/).

## Шаг 1. Создайте новый проект
Создайте новый проект в предпочитаемой вами среде разработки .NET (например, Visual Studio) и добавьте ссылки на библиотеку Aspose.Slides для .NET.

## Шаг 2. Импортируйте необходимые пространства имен
В свой проект импортируйте необходимые пространства имен для работы с Aspose.Slides:

```csharp
using Aspose.Slides;
using Aspose.Slides.ActiveXControls;
```

## Шаг 3. Загрузите презентацию
Загрузите презентацию PowerPoint, в которую вы хотите добавить связанное видео:

```csharp
string presentationPath = "path_to_your_presentation.pptx";
using (Presentation presentation = new Presentation(presentationPath))
{
    // Здесь будет ваш код для добавления связанного видео.
}
```

## Шаг 4. Добавьте элемент управления ActiveX
 Создайте экземпляр`IOleObjectFrame` интерфейс для добавления элемента управления ActiveX на слайд:

```csharp
ISlide slide = presentation.Slides[0]; // Выберите слайд, на который вы хотите добавить видео.
IOleObjectFrame oleObjectFrame = slide.Shapes.AddOleObjectFrame(0, 0, 640, 480, "Video", "ShockwaveFlash.ShockwaveFlash.10");
```

В приведенном выше коде мы добавляем на слайд рамку управления ActiveX размером 640x480. Мы указываем ProgID для элемента управления ActiveX ShockwaveFlash, который обычно используется для встраивания видео.

## Шаг 5. Установите свойства элемента управления ActiveX
Задайте свойства элемента управления ActiveX, чтобы указать связанный источник видео:

```csharp
oleObjectFrame.ObjectData = Encoding.UTF8.GetBytes("YourVideoPathHere"); // Замените фактическим путем к видеофайлу.
oleObjectFrame.AlternativeText = "Linked Video";
```

 Заменять`"YourVideoPathHere"` с фактическим путем к вашему видеофайлу.`AlternativeText` Свойство предоставляет описание связанного видео.

## Шаг 6: Сохранить презентацию
Сохраните измененную презентацию:

```csharp
string outputPresentationPath = "output_presentation.pptx";
presentation.Save(outputPresentationPath, SaveFormat.Pptx);
```

## Часто задаваемые вопросы:

### Как указать размер и положение связанного видео на слайде?
Вы можете настроить размеры и положение рамки управления ActiveX, используя параметры файла`AddOleObjectFrame` метод. Четыре числовых аргумента представляют координаты X и Y верхнего левого угла, а также ширину и высоту кадра соответственно.

### Могу ли я связать видео разных форматов, используя этот подход?
Да, вы можете связывать видео различных форматов, если для этого формата доступен соответствующий элемент ActiveX. Например, элемент управления ActiveX ShockwaveFlash, используемый в этом руководстве, подходит для Flash-видео (SWF). Для других форматов вам может потребоваться использовать другие ProgID.

### Есть ли ограничение на размер связанного видео?
Размер связанного видео может повлиять на общий размер и производительность вашей презентации. Рекомендуется оптимизировать видео для просмотра в Интернете, прежде чем связывать их с презентацией.

### Заключение:
Следуя шагам, описанным в этом руководстве, вы можете легко связать видео через элемент управления ActiveX в презентации с помощью Aspose.Slides для .NET. Эта функция позволяет создавать увлекательные интерактивные презентации, в которые легко включается мультимедийный контент.

 Для получения более подробной информации и дополнительных опций вы можете обратиться к[Документация Aspose.Slides для .NET](https://reference.aspose.com/slides/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
