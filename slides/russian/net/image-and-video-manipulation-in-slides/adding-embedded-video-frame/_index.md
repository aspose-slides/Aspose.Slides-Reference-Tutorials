---
"description": "Улучшите свои презентации встроенными видео с помощью Aspose.Slides для .NET. Следуйте нашему пошаговому руководству для бесшовной интеграции."
"linktitle": "Aspose.Slides — Добавление встроенных видео в презентации .NET"
"second_title": "API обработки PowerPoint Aspose.Slides .NET"
"title": "Aspose.Slides — Добавление встроенных видео в презентации .NET"
"url": "/ru/net/image-and-video-manipulation-in-slides/adding-embedded-video-frame/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides — Добавление встроенных видео в презентации .NET

## Введение
В динамичном мире презентаций интеграция элементов мультимедиа может значительно повысить вовлеченность. Aspose.Slides для .NET предоставляет мощное решение для включения встроенных видеокадров в слайды презентации. Это руководство проведет вас через весь процесс, разбив каждый шаг на части, чтобы обеспечить бесперебойный опыт.
## Предпосылки
Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующее:
- Библиотека Aspose.Slides для .NET: Загрузите и установите библиотеку с сайта [страница релиза](https://releases.aspose.com/slides/net/).
- Медиаконтент: у вас должен быть видеофайл (например, «Wildlife.mp4»), который вы хотите встроить в свою презентацию.
## Импорт пространств имен
Начните с импорта необходимых пространств имен в ваш проект .NET:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Шаг 1: Настройка каталогов
Убедитесь, что в вашем проекте есть необходимые каталоги для файлов документов и мультимедиа:
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(dataDir, "VideoFrame_out.pptx");
// Создайте каталог, если его еще нет.
bool IsExists = Directory.Exists(dataDir);
if (!IsExists)
    Directory.CreateDirectory(dataDir);
```
## Шаг 2: Создание экземпляра класса представления
Создайте экземпляр класса Presentation для представления файла PPTX:
```csharp
using (Presentation pres = new Presentation())
{
    // Получить первый слайд
    ISlide sld = pres.Slides[0];
```
## Шаг 3: Вставьте видео в презентацию
Используйте следующий код для встраивания видео в презентацию:
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
## Шаг 4: Добавьте видеокадр
Теперь добавьте видеокадр к слайду:
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
## Шаг 5: Установка свойств видео
Установите видео в видеокадр и настройте режим воспроизведения и громкость:
```csharp
vf.EmbeddedVideo = vid;
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
## Шаг 6: Сохраните презентацию
Наконец, сохраните файл PPTX на диск:
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
Повторите эти шаги для каждого видео, которое вы хотите встроить в презентацию.
## Заключение
Поздравляем! Вы успешно добавили встроенный видеокадр в свою презентацию с помощью Aspose.Slides for .NET. Эта динамическая функция может поднять ваши презентации на новую высоту, увлекая вашу аудиторию мультимедийными элементами, бесшовно интегрированными в ваши слайды.
## Часто задаваемые вопросы
### Могу ли я встроить видео в любой слайд презентации?
Да, вы можете выбрать любой слайд, изменив индекс в `pres.Slides[index]`.
### Какие форматы видео поддерживаются?
Aspose.Slides поддерживает множество видеоформатов, включая MP4, AVI и WMV.
### Могу ли я настроить размер и положение видеокадра?
Конечно! Отрегулируйте параметры в `AddVideoFrame(x, y, width, height, video)` по мере необходимости.
### Есть ли ограничение на количество встраиваемых видео?
Количество встроенных видео обычно ограничено возможностями вашего программного обеспечения для презентаций.
### Как я могу получить дополнительную помощь или поделиться своим опытом?
Посетите [Форум Aspose.Slides](https://forum.aspose.com/c/slides/11) для поддержки сообщества и обсуждений.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}