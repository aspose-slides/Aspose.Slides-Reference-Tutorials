---
title: Aspose.Slides — добавление встроенных видео в презентации .NET
linktitle: Aspose.Slides — добавление встроенных видео в презентации .NET
second_title: Aspose.Slides .NET API обработки PowerPoint
description: Улучшите свои презентации с помощью встроенных видео с помощью Aspose.Slides для .NET. Следуйте нашему пошаговому руководству для бесшовной интеграции.
weight: 19
url: /ru/net/image-and-video-manipulation-in-slides/adding-embedded-video-frame/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides — добавление встроенных видео в презентации .NET

## Введение
В динамичном мире презентаций интеграция мультимедийных элементов может значительно повысить вовлеченность. Aspose.Slides for .NET предоставляет мощное решение для включения встроенных видеокадров в слайды вашей презентации. Это руководство проведет вас через весь процесс, разбив каждый шаг, чтобы обеспечить бесперебойную работу.
## Предварительные условия
Прежде чем мы углубимся в руководство, убедитесь, что у вас есть следующее:
-  Aspose.Slides для библиотеки .NET: загрузите и установите библиотеку из[страница выпуска](https://releases.aspose.com/slides/net/).
- Медиа-контент: у вас есть видеофайл (например, «Wildlife.mp4»), который вы хотите встроить в свою презентацию.
## Импортировать пространства имен
Начните с импорта необходимых пространств имен в ваш проект .NET:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Шаг 1. Настройка каталогов
Убедитесь, что в вашем проекте есть необходимые каталоги для документов и медиафайлов:
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(dataDir, "VideoFrame_out.pptx");
// Создайте каталог, если он еще не существует.
bool IsExists = Directory.Exists(dataDir);
if (!IsExists)
    Directory.CreateDirectory(dataDir);
```
## Шаг 2. Создание экземпляра класса представления
Создайте экземпляр класса Presentation для представления файла PPTX:
```csharp
using (Presentation pres = new Presentation())
{
    // Получить первый слайд
    ISlide sld = pres.Slides[0];
```
## Шаг 3. Вставьте видео в презентацию
Используйте следующий код, чтобы встроить видео в презентацию:
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
## Шаг 4: Добавьте видеокадр
Теперь добавьте видеокадр на слайд:
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
## Шаг 5. Установите свойства видео
Установите видео в видеокадр и настройте режим воспроизведения и громкость:
```csharp
vf.EmbeddedVideo = vid;
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
## Шаг 6. Сохраните презентацию
Наконец, сохраните файл PPTX на диск:
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
Повторите эти шаги для каждого видео, которое вы хотите встроить в презентацию.
## Заключение
Поздравляем! Вы успешно добавили встроенный видеокадр в свою презентацию с помощью Aspose.Slides for .NET. Эта динамическая функция может поднять ваши презентации на новую высоту, захватывая аудиторию мультимедийными элементами, легко интегрированными в ваши слайды.
## Часто задаваемые вопросы
### Могу ли я встроить видео в любой слайд презентации?
 Да, вы можете выбрать любой слайд, изменив указатель в`pres.Slides[index]`.
### Какие форматы видео поддерживаются?
Aspose.Slides поддерживает множество видеоформатов, включая MP4, AVI и WMV.
### Могу ли я настроить размер и положение видеокадра?
 Абсолютно! Настройте параметры в`AddVideoFrame(x, y, width, height, video)` по мере необходимости.
### Есть ли ограничение на количество видео, которые я могу вставить?
Количество встроенных видео обычно ограничено возможностями вашего программного обеспечения для презентаций.
### Как я могу обратиться за дополнительной помощью или поделиться своим опытом?
 Посетить[Форум Aspose.Slides](https://forum.aspose.com/c/slides/11) за поддержку сообщества и обсуждения.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
